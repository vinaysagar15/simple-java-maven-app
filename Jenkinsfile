node(label:'slave1') {
    stage('clone')
    {
        git 'https://github.com/vinaysagar15/simple-java-maven-app.git'
    }
    stage('maven')
    {
        def mvnHome= tool name: 'maven', type: 'maven'
        sh "${mvnHome}/bin/mvn clean package " 
    }

   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
   }
 
   }

