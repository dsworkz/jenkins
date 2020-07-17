###Pipeline projects: 
Pipeline based projects are configured via JenkinsFile to define the application lifecycle as workflow.
In short, Pipelines are Jenkins jobs enabled by the Pipeline (formerly called “workflow”) plugin and built with simple text scripts that use a Pipeline DSL (domain-specific language) based on the Groovy programming language.
A quick tutorial on pipeline:
Modules includes:

# Node:  
In a simple context- node means a computer/machine which is connected as slave/runner. By enlisting executer Jenkins performs build on the node by performing the activity listed in steps.

# Agent: 
to perform build/deploy activities on any delegated agent.
```
pipeline {
	agent any
}
```

# Stages:  
a stage is step to call the supported APIs. Pipeline syntax is comprised of stages. Each stage can have one or more build steps within it.
```
pipeline {
	agent any
	stages {
	}
}
```

# Stage:
Jenkins graphically splits pipeline execution based on the defined stages and displays their duration and whether it was successful or not.
```
pipeline {
	agent any
	stages {
		stage ('build') {
			...
		}
		stage ('test: integration-&-quality') {
			...
		}
		stage ('test: functional') {
			...
		}
		stage ('test: load-&-security') {
			...
		}
		stage ('approval') {
			...
		}
		stage ('deploy:prod') {
			...
		}
	}
}
```

# Step:  
step is a single task that is part of sequence which tells Jenkins on what to do.
```
pipeline {
	agent any
	stages {
		stage(‘get’) {
			steps {
				sh ‘curl google.com’
			}
		}
	}
}
```
