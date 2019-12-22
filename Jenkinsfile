     node('slave') {
        def gradleHome= tool 'gradle4'
          try {  
               stage('checkout') {
                    checkout scm
                    }
        
               stage('build') {
                     sh "${gradleHome}/bin/gradle build"
                    }
          } catch (ex) {
            echo 'Error occurred'
          }
         stage ('post') {
              if(CurrentBuild.results == 'SUCCESS') {
                addBadge(icon: success.gif, text: 'Success')
              }
              if(CurrentBuild.results == 'FAILURE') {
                addBadge(icon: error.gif, text: 'Failure'
              }
          }
     }
