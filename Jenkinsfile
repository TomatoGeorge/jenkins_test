pipeline { // 최 상단 element로 정의되어 있어야 한다.
    agent any // pipeline 블록 내 최 상단에 정의되어야 하며, 말 그대로 실행할 Agent가 할당된다. 여기서 'any'는 사용가능한 어떠한 agent로도 실행해도 된다는 걸 나타낸다. 이는 pipeline 아래 위치해도 되고 각 stage 블록에 위치해도 된다.
 
    stages {
        stage('Build') { // stage는 Pipeline의 단계를 나타낸다.
            steps { // 해당 stage에서 실행할 명령을 기술하는 부분이다.
                sh 'make' // 주어진 shell 명령을 수행한다.
            }
        }
        stage('Test'){
            steps {
                sh 'make check'
                junit 'reports/**/*.xml' // junit 플러그인을 통해 제공하는 기능으로, 테스트 보고서를 집계한다.
            }
        }
        stage('Deploy') {
            steps {
                sh 'make publish'
            }
        }
    }
}
