stage('stage1') {
when {
environment name: 'STATUS', value: 'true'
}
steps {
            echo 'stage1'
            script{
            println "Status " + env.STATUS
            }
}
}
stage('stage2') {
when {
environment name: 'STATUS', value: 'false'
}
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
when {
environment name: 'STATUS', value: 'false'
}
steps {
            echo 'stage3'
            script{
                println env.STATUS
            }
}
}
