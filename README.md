## AzureFunctions with different scenarios in Java 

*Start the azure functions creation by follwoing below steps*

* Install azure core tool
* Install azure cli
* Java and Maven(path configured)

Install dotnet sdk as well since running azure function we get a warning of non-availability of `dotnet.exe`

**Run the below mvn command to start with default**

mvn archetype:generate "-DarchetypeGroupId=com.microsoft.azure" "-DarchetypeArtifactId=azure-functions-archetype" "-DjavaVersion=8"

place -DjavaVersion=8 based on you Java version

Entering above command ask for both groupid and artifactid enter the values. when ask for HTTPTrigger enter `Y`

After that a default project is generate with HTTPTrigger

Then run `mvn clean install package`

Try to run the azure function using below command
`mvn azure-functions:run`

if you came across the below issue while running the above command 

`Value cannot be null. (Parameter 'provider')`

then run the below command to install the extensions.

Try to remove extension tag from host.json in your user folder

`func extensions install --package Microsoft.Azure.WebJobs.Extensions.Storage --version 4.0.2`

Note: Above thing worked for me

Then running the command will generate a HTTPTrigger to test local

`http://localhost:7071/api/HttpExample`








