node ("worker1") {
//    stage("Source") {
//        git url: 'https://github.com/mimikuku/testJenkins.git'
//    }
    stage("Build") {
        sh "echo Gradle build wil go here"
        sh "echo ${currentBuild}"
    }
    // stage("Show variables") {
    //     def loginInfo = input id: 'SomeID', message: 'Choose', parameters: [
    //         string(defaultValue: '', description: '', name: 'userid', trim: false),
    //         password(defaultValue: '', description: '', name: 'passwd')
    //     ]
    //     echo "Username = " + loginInfo['userid']
    //     echo "Password = ${loginInfo['passwd']}"
    //     echo loginInfo.userid + " " + loginInfo.passwd
    // }
    stage("timeout") {
        timeout(time:15, unit:'SECONDS') {
        waitUntil {
            def ret = sh returnStatus: true,
            script: 'test -e /home/jenkins2/marker.txt'
            return (ret == 1)
        }
        }
    }
    stage("new_word") {
        sh "echo Add new strings"
    }
}
