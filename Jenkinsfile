pipeline {
  stages {
    stage('Master node') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        sh 'echo "I am on master node and my hostname is `hostname`"'
      }
    }

  
      parallel {
        stage('Node 1') {
          agent {
            node {
              label 'node1'
            }

          }
          steps {
            sh '''echo "I am on node1 and my hostname is `hostname`"
echo "I have come here from master node"'''
          }
        }

        stage('Node 2') {
          agent {
            node {
              label 'node2'
            }

          }
          steps {
            sh '''echo "I am on node 2 and my hostname is `hostname`"
echo "I am coming here from master node"'''
          }
        }

      }
    }

  }
