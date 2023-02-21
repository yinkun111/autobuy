pipeline {
    agent any
    stages {
        stage('拉取git代码') {
            steps {
                checkout scmGit(branches: [[name: '${tag}']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/yinkun111/autobuy.git']])
            }
        }
        stage('构建build') {
            steps {
                echo '构建成功'
            }
        }
        stage('代码质量检测') {
            steps {
                echo '检测成功'
            }
        }
        stage('docker制作镜像') {
            steps {
                sh '''mv jenkins.py loopsh docker/
                docker build -t ykapp2:$tag docker/'''
            }
        }
        stage('镜像推送到harbor') { 
            steps {
               sh '''docker login -u admin -p Harbor12345 192.168.75.128:80
                docker tag ykapp2:$tag 192.168.75.128:80/harbor/ykapp2:$tag
                cker push 192.168.75.128:80/harbor/${JOB_NAME}:$tag'''
            }
        }    
        stage('通过publish over ssh通知服务器') {
            steps {
                echo '通知远端服务器成功'
            }
         }
    }

}

