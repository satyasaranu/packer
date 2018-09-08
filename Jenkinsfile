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
        stage("build AMI") {
        steps {
           
            withAWS(region:'us-east-1',credentials:'d4ccaa7b-7efd-4318-9592-1f8a44cd79fb')
            {
            sh "echo Packer is building AMI using RHEL image: ${params.AMI_ID} in ${params.AWS_REGION} Region"
            sh "${packer_home}/packer build -var ami_name=${params.AMI_ID} -var region=${params.AWS_REGION}  packer.json"    
            }
            }
    }
    }
}
