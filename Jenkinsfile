pipeline {

agent any



stages {

stage('Checkout') {

steps {

git 'https://github.com/sharadrajore/wfa-jenkins.git'

}

}

stage('Build'){

steps{

tool name: 'maven', type: 'maven'

bat 'mvn package'

}

}

stage('Deploy'){

steps{

deploy adapters: [tomcat8(credentialsId: 'tomcat-cred',

path: '', url: 'http://localhost:9090/')],

contextPath: 'servlet-jsp-maven',

onFailure: false,

war: '**/*.war'

}

}



}

}
