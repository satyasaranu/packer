pipeline {
    agent any
    environment {
        packer_home = tool('packer-1.2.5')
    }
    parameters {
        string(name:'AMI_ID', defaultValue:'ami-6871a115', description:'please enter AMI ID')
        string(name:'AWS_REGION', defaultValue:'us-east-1', description:'please enter Region')
    }
    stages {
        stage("build") {
        steps {
           
            withAWS(region:'us-east-1',credentials:'cafb2209-ed5a-4bf1-a9cb-b244e7b77186')
            {
            sh "${packer_home}/packer build -var 'ami_name=ami-6871a115' -var 'region=us-east-1' packer.json"    
            }
            }
    }
    }
}
