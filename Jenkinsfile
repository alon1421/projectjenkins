pipeline {
  agent { node { label 'slave01' } }
  parameters {
    choice(
      name: 'Language',
      choices: ['All', 'C', 'Py', 'Bash'],
      description: 'Passing the Environment'
    )
  }
  
  stages {
  // start python steps
    stage('First step of python') {
     when {
       expression {
         env.Language == 'All'||
         env.Language == 'Py'
     }
    }
      steps {
        sh ' python3 /home/alon/firststeppy.py'
      }
  }
	stage('Second step of python') {
     when {
       expression {
         env.Language == 'All'||
         env.Language == 'Py'
     }
    }
      steps {
        sh ' python3 /home/alon/secondsteppy.py'
      }
  }
  // end python steps
  // start C steps
    	stage('First step of C') {
     when {
       expression {
         env.Language == 'All'||
         env.Language == 'C'
     }
    }
      steps {
        sh '/home/alon/firststepc'
      }
  }
    stage('Second step of C') {
     when {
       expression {
         env.Language == 'All'||
         env.Language == 'C'
     }
    }
      steps {
        sh '/home/alon/secondstepc'
      }
  }
    stage('Third step of C') {
     when {
       expression {
         env.Language == 'All'||
         env.Language == 'C'
     }
    }
      steps {
        sh '/home/alon/thirdstepc'
      }
  }
  // end C steps
  // start Bash steps
      	stage('First step of Bash') {
     when {
       expression {
         env.Language == 'All'||
         env.Language == 'Bash'
     }
    }
      steps {
        sh 'bash /home/alon/firststepbash.sh'
      }
  }
    stage('Second step of Bash') {
     when {
       expression {
         env.Language == 'All'||
         env.Language == 'Bash'
     }
    }
      steps {
        sh 'bash /home/alon/secondstepbash.sh'
      }
	    
  }
	  stage('Saving Results') {
         steps {
            echo 'Saving Results process..'
            sh '''
	      report_file="${HOME}/Documents/Deployment/report"
              mkdir -p ${HOME}/Documents/Deployment/              
              if [ -f "${report_file}" ]; then
                echo "file ${report_file} exists"
              else
	              touch ${report_file}
              fi
	      date >> ${report_file}
	      echo "USER=$USER JOB_NAME=$JOB_NAME" >> ${report_file}
              echo "Build Number $BUILD_NUMBER" >> ${report_file}
              cat "${WORKSPACE}/Scripts/results" >> ${report_file}
	      echo "#############################" >> ${report_file}
            '''
         }
      }
}
}
