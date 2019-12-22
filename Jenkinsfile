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
            echo "Build result is " + currentBuild.result
             if ( currentBuild.result == 'SUCCESS') {
               addBadge(icon: 'green.gif', text: 'Build Succeeded')
               }
               if (currentBuild.result == 'FAILURE') {
                    addBadge(icon: 'red.gif', text: 'Build Failed')
               } 
          }
     }
