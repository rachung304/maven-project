node {
    checkout scm
    
    stage('build') {
        try {
            def mvnHome = tool 'LocalMaven'
            
            if (isUnix()) {
                echo 'this is a Unix System'
                sh "${mvnHome}/bin/mvn -B verify"
            } else {
                echo 'this is a pc'
                bat "${mvnHome}/bin/mvn -B verify"
            }
        } catch (e) {
            currentBuild.result = 'Failure'
        }
    }
    
    stage('notification') {
        if (currentBuild.result )
    }
}