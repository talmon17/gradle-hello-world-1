     node('slave') {
        def gradleHome= tool 'gradle4'
        currentBuild.result = 'SUCCESS'
          
          try {  
               stage('checkout') {
                    checkout scm
                    }
        
               stage('build') {
                     sh "${gradleHome}/bin/gradle build"
                    }
          } catch (ex) {
            currentBuild.result == 'FAILURE'
            echo 'Error occurred'
          }
         stage ('post') {
              echo currentBuild.result
              if(currentBuild.result == 'SUCCESS') {
                addBadge(icon: success.gif, text: 'Success')
              }
              if(currentBuild.result == 'FAILURE') {
                addBadge(icon: error.gif, text: 'Failure')
              }
          }
     }
