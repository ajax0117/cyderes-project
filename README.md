---------CYDERES Logstash sample for telemetry engineer-------------------

Total time taken for project was 7.5 hrs 


Logstash Install:
Researched and installed Logstash8.6.2 on my WIN11 PC. Ran some of the sample in-out pipelines to get the basic feel of how Logstash processes data.

Researched input, output and filter plugins to see what would be the best choice for this particular project. Since I was using a file local to the PC and was also writing the file locally I chose the logstash-input-file and the logstash-output-file plugins to ingest the log file and write the new formatted data to a file.

Most time was spent researching and testing different filter plugins and scenarios. I tried multiple filters and ended up using dissect, kv and mutate for the filter plugins.

The Logstash pipeline I created is as follows

1. Ingest c:\logstash\securitydata.log into the pipeline using the file input filter. 
2. Filter data with dissect to map known fields 
3. Use kv to parse the key value pairs
4. Use mutate to remove certain fields from the output, rename some fields to match specific requirement in project and to replace the data in the severity field so it is read as a string versus a number.
5. Write the file to c:\logstash\output.json - by default the file output plugin writes the file in JSON.
6. Open file to test that the data written was formatted properly and readable
