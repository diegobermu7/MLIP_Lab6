pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'

                # ✅ Initialize Conda (Modify the path if necessary)
                source /opt/anaconda3/etc/profile.d/conda.sh
                conda activate myenv  # Replace 'myenv' with your actual environment name

                # ✅ Run pytest
                pytest tests/  # Modify if your test folder is different

                echo 'pytest completed successfully'
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}