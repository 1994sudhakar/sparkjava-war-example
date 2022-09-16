pipeline
{
  environment {
    registry = "sudhakar/docker"
    registryCredential = "mydockerhub"
    dockerImage = ""
  }
  agent any
  tools { maven "maven363" }
  stages {
    stage ("clone Git scm ")
    steps {
      git "url"
    }
  }
  stage("build")
  steps {
    sh script 'mvn clean test package'
  }
  stage ("build the docker Images")
  {
    steps {
      script{ dockerImage = docker.build registry + "$BUILD_NUMBER"
            }
    }
  }
  stage ( "push to registry")
  {
    steps {
      script 
      docker.withRegistry(".registryCredential) { dockerImage.push)
                          }
                          }
                          }
                          }
                          
                          stage ("deploy to kuberntes")
                          steps {
                            sh "helm install --name myrelease --values myvalues.yaml ./microservice1"
                          }
                          }}}
                          
                          
       
 
