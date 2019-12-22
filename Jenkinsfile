     node('slave') {
        stage('checkout') {
            checkout scm
        }
        
        stage('build') {
          def gradleHome= tool 'gradle4'
          sh "${gradleHome}/bin/gradle build"
        }
        
        stage('post') {
            addBadge(icon: green.gif, text: "it's succesfull")
        }
     }
