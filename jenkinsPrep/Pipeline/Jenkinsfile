//CODE_CHANGES = getGitChange()
pipeline {
    agent any
    environment{
        NEW_VERSION = '1.2.1'
        CRED = credentials('credentialsID') // for using credentials from jenkins server
    }
    parameters{
        string(name: 'Version', defaultValue:'', description: 'version to deploy on prod')
        choice(name: 'Version', choices:['1.2.1','1.2.3'],description:'')
        booleanParam(name: 'executeTests', defaultValue: true, description:'')
    }
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build"){
            when {
                expression {
                    //CODE_CHANGES ==true
                }
            }
            steps{
                echo "building app"
                echo "building version ${NEW_VERSION}"
            }
        }

        stage("test"){
            when{
                expression {
                    params.executeTests //== true
                }
            }
            steps{
                echo "testing app ...."
            }
        }

        stage("deploy"){
            input {
                message "Select env to deploy"
                ok "Done"
                parameters{
                    choice(name: 'ENV_one', choices:['dev','staging','prod'],description:'')
                    choice(name: 'ENV_two', choices:['dev','staging','prod'],description:'')
                }
            }
            steps{
                script {
                    // inside script input
                    // env.ENV = input message: "select env",message "Select the environment to deploy",ok "Done",parameters {choice(name: 'ENV_one', choices:['dev','staging','prod'],description:''}
                    gv.deploy()
                    echo "deplying for environments ${ENV_one} and ${ENV_two}"
                }
                
            }
        }
                // or directly apply here
                // withCredentials([
                //     usernamePassword(credentials: 'server-cred-id', usernameVariable: 'USER', passwordVariable: 'PWD')
                // ]){
                //     echo "some script ${USER} ${PWD}"
                // }

    }
}

post {
    always{
        //
    }
    success{
        //
    }
    failure{
        //
    }
}
