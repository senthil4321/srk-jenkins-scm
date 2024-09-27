stage('stage1') {

steps {
            echo 'stage1'
            script{
            println "Status " + env.STATUS
            }
}
}
stage('stage2') {

steps {
            echo 'stage2'
            script{
            println "Status "+ env.STATUS
            env.STATUS = true
            println "Status "+ env.STATUS
            }
}
}
stage('stage3') {

steps {
            echo 'stage3'
            script{
                println env.STATUS
            }
}
}
