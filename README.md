# Facebook ZIP Analyzer - Explore Your Facebook Data Using ELK
This repository lets you explore, visualize and understand what data Facebook has about you.<br>
All you need to do is go to the "Download Your Information" page, Download your private <b>JSON</b> archive at https://facebook.com/dyi/
## Setup
After you downloaded the archive, unzip it into the the folder "my_data", to the directory tree will look like this:
```code
mkdir my_data
# unzip your archive to my_data directory
# The dir tree should be:
/my_data/<your_facebook_name>/...
```
Then, install docker-compose and docker locally.<br>
Now, simply run the stack and see your data. 
The archive will be streamed to the stack from the files you just added to "my_data" directory using Kigstash, indexed in ElasticSearch and visualized in Kibana.
```
# Optional - Install Docker:
#                            sudo snap install docker
#                            (https://docs.docker.com/get-docker/)
# Optional - Install Compose:
#                            https://docs.docker.com/compose/install/
# Run the stack:
docker-compose up
```
## Accessing The Dashboard
Now your data will be streamed, and within a minute you should see it on Kibana on http://localhost:5601/.
## See The Stack Logs
```code
docker-compose logs -f
```
## Add More Data To Logstash
You can add more files to the pipeline, by adding files to /logstash/pipeline/ and replacing the file path, and fields names to split.
