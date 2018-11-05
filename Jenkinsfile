pipeline {
    agent any 
    stages {
        stage('checkout') { 
            steps {
                git 'https://github.com/vanimadhav/warrepo.git'
            }
        }
        stage('build') { 
            steps {
                sh'mvn clean package'
            }
             }
             stage ('deploy s3') {
                steps {
                    s3Upload consoleLogLevel: 'INFO', dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'warfile87', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-2', showDirectlyInBrowser: false, sourceFile: '**/*.war', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'SUCCESS', profileName: 's3', userMetadata: []
        }
        }
    }
  }
