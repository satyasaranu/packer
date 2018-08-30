pipeline {
    agent any
    environment {
        packer_home = tool('packer-1.2.5')
    }
    stages {
        stage("build") {
        steps {
           
            withAWS(region:'us-east-1',credentials:'satya-aws-cred')
            {
            sh '${packer_home}/packer build packer.json'    
            }
            }
    }
    }
}
