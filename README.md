# Getting started with Amazon Timestream with Java v2

This sample application shows how you can create a database and table, populate the table with ~126K rows of sample data, and run sample queries with Amazon Timestream.

----
## How to use it

Ensure your Java SDK and runtime are 1.8 or higher.

1. Install maven: https://maven.apache.org/install.html

2. Go to Timestream Java V2 sample app directory

   3. You can compile and run your source code with the below   command:
       ```shell
      mvn clean compile
      mvn exec:java -Dexec.mainClass="com.amazonaws.services.timestream.Main" -Dexec.args="--type BASIC --region us-west-2 --skip_deletion"
       ``` 
      NOTE: You might need to change the version of timestreamwrite and timestreamquery dependencies in `pom.xml` file based on the version of SDK jar you are using.

4. To run with sample application and ingest data from sample csv data file, you can use the following command:
   ```shell
   mvn clean compile
   mvn exec:java -Dexec.mainClass="com.amazonaws.services.timestream.Main" -Dexec.args="--type BASIC --region us-west-2 --skip_deletion --inputFile ./data/sample.csv"
   ```

5. To run with sample application and include database CMK update to a kms "valid-kms-id" registered in your account run
   ```shell
   mvn clean compile
   mvn exec:java -Dexec.mainClass="com.amazonaws.services.timestream.Main" -Dexec.args="--type BASIC --region us-west-2 --skip_deletion --kmsId valid-kms-id"
   ``` 
6. To run sample application for unload queries
   ```shell
   mvn clean compile
   mvn exec:java -Dexec.mainClass="com.amazonaws.services.timestream.Main" -Dexec.args="--type UNLOAD --region us-west-2 --skip_deletion --inputFile ./data/sample_unload.csv"
   ``` 
7. To run sample application for composite partition key
   ```shell
   mvn clean compile
   mvn exec:java -Dexec.mainClass="com.amazonaws.services.timestream.Main" -Dexec.args="--type COMPOSITE_PARTITION_KEY --region us-west-2 --skip_deletion"
   ```