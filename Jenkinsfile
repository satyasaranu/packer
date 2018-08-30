pipeline {
    agent any
    environment {
        packer_home = tool('packer-1.2.5')
    }
    stages {
        stage("build") {
        steps {
           
            withAWS(region:'us-east-1',credentials:'cafb2209-ed5a-4bf1-a9cb-b244e7b77186')
            {
            sh '${packer_home}/packer build packer.json'    
            }
            }
    }
    }
}
