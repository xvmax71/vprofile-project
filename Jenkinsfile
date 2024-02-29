pipeline {
    agent any
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-1.8.0-openjdk-amd64' // Update this path according to your JDK installation directory
        SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin123'
        RELEASE_REPO = 'vprofile'
        CENTRAL_REPO = 'vpro-maven-central'
        NEXUSIP = '54.147.224.160'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vprofile-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }
    stages {
        stage('Build') {
            steps {
                withEnv(['JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64']) {
                    sh 'mvn -s settings.xml -DskipTest install'
                }
            }
        }
    }
}
pipeline {
    agent any 
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }

    environment {
        SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin123'
        RELEASE_REPO = 'vprofile'
        CENTRAL_REPO = 'vpro-maven-central'
        NEXUSIP = '54.147.224.160'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vprofile-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps {
                withEnv(['JAVA_HOME=/usr/lib/jvm/']) {
                    sh 'mvn -s settings.xml -DskipTest install'
                }
            }
        }
    }
}
