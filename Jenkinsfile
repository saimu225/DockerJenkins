pipeline{
  agent any
  stages{
    stage('Checkout'){
          steps{
            git url:'https://github.com/saimu225/DockerJenkins.git', branch:'main'
          }
          }

          stage('Build Image'){
            steps{
              bat 'docker build -t mywebsite .'
            }
          }
          
          stage('Stop Old Containers'){
            steps{
              bat 'docker stop mycont || exit 0'
              bat 'docker rm mycont || exit 0'
            }
          }

          stage('Run Image -Contanerize'){
            steps{
              bat 'docker run -d -p 7000:80 --name mycont mywebsite'
              }
           }
        }
        }
