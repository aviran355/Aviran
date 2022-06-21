properties([githubProjectProperty(displayName: '', projectUrlStr: 'https://github.com/aviran355/Shared.git/'), pipelineTriggers([pollSCM('* * * * *')])])
node { 
    stage("clone"){
        git branch: 'main', url: "https://github.com/aviran355/top-spring-boot-docker.git"
    }
    stage("one"){
        sh "pwd; cd demo; /usr/local/bin/docker build --build-arg JAR_FILE=target/*.jar -t myorg/myapp ."
    }
    stage("two"){
        sh "/usr/local/bin/docker run -p 8090:80 myorg/myapp"
    }
    stage("three"){
        sh "curl localhost:8090"
    }
    stage("four"){
        sh "/usr/local/bin/docker rm -f test1"
    }
}
