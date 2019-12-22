     node('slave') {
        def gradleHome= tool 'gradle4'
          
        stage('checkout') {
            checkout scm
        }
        
        stage('build') {
          
          sh "${gradleHome}/bin/gradle build"
        }

         stage ('post') {
               sh "${gradleHome}/bin/gradle test"    
          }
     }
