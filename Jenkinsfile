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
        sh 'bash firststepbash.sh'
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
        sh 'bash secondstepbash.sh'
      }
  }
}
}



