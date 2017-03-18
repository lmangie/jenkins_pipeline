#!groovy

pipeline{
	stages{
		stage ("testing") {
			parallel (
				"stream 1" : {
								 node {
									   sh "echo hstream1"
								   }
							   },
				"stream 2" : {
								 node("My_node") {
									   sh "curl -X POST http://localhost:8080/job/gameoflife/build --data token=token -H Jenkins-Crumb:34cfe5ef2ff487e5b6a7dff4f4a2b0c2"
								   }
							   }
					  )
		}
		stage ("printing"){
			parallel (
				"stream 1" : {
								 node {
									   sh "echo hstream1"
								   }
							   },
				"stream 2" : {
								 node("My_node") {
									   sh "echo hello2"
								   }
							   }
					  )
		}
	}
}
