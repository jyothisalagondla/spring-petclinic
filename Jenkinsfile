node ('build_java_11') {
    stage('sourcecode')  {
        // get the code from git repo on scripted branch
        git branch: 'scripted', url: 'https://github.com/jyothisalagondla/spring-petclinic.git'
    }
    
    stage('build the code')  {
        sh 'mvn package'
    }

    stage('junit test result') {
        junit '**/surefire-reports/*.xml'
        archiveArtifacts artifacts: '**/*.war', followSymlinks: false
    }
}
    