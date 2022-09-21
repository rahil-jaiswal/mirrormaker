# mirrormaker

Following is Kafka Mirrormaker
(Legacy Mirroring)

Here we have Source and Target nodes where source is actively consuming from the client application and target from source.
entrypoint.sh is the file which will start mirroring. 


To build Docker Images run following command -> 
        "docker build -t mirrormaker:1.1 -f {PATH}/Dockerfile"

To run Docker Image as a container execute following command ->
	"docker run -d mirrormaker:1.1 --env-file env-file"

You need to modify the source producer and target consumer addresses in env-file.
If any changes on configuration or additional parmater, checkout config directory.

You can export the mirrormaker to your system and use it with Kubernetes or Docker-Compose.
But make sure to pass following parameters as ENV (Server Parameters are in format {IP}:{PORT} and comma seperated)
	a. SINK_CLUSTER_BOOTSTRAP_SERVERS
	b. SOURCE_CLUSTER_BOOTSTRAP_SERVERS
 	c. SOURCE_CLUSTER_CONSUMER_GROUP
