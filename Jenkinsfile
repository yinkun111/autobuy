pipeline {
    agent any
    stages {
        stage('拉取git代码') {
            steps {
                echo 'Hello World'
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
                echo '制作镜像成功'
            }
        }
        stage('镜像推送到harbor') {
            steps {
                echo '推送镜像成功'
            }
        }    
        stage('通过publish over ssh通知服务器') {
            steps {
                echo '通知远端服务器成功'
            }
         }
    }

}

