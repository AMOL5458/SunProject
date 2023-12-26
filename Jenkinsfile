pipeline {
    agent any

    stages {
        stage ('SCM') {
            steps {
                git branch: 'main', url: 'https://AMOL5458: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@github.com/AMOL5458/SunProject.git'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_pRkH7tiN_3ODAFA6MONK1Nwaens | /usr/bin/docker login -u amol1701 --password-stdin'
            }
        }
        stage ('docker build image') {
            steps {
                sh '/usr/bin/docker image build -t amol1701/myproject .'
            }
        }
        stage ('docker push image') {
            steps {
                sh '/usr/bin/docker image push amol1701/myproject'
            }
        }
        stage ('docker remove service') {
            steps {
                sh '/usr/bin/docker service rm myservice'
            }
        }
        stage ('docker create service') {
            steps {
                sh '/usr/bin/docker service create --replicas 5 --name myservice -p 8080:80 amol1701/myproject'
            }
        }
    }
} 
