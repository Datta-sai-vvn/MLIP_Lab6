pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat '''
                echo In C or Java, we can compile our program in this step.
                echo In Python, we can build our package here or skip this step.
                '''
            }
        }

        stage('Test') {
            steps {
                bat '''
                echo Test Step: We run testing tool like pytest here.

                :: Create virtual environment if not exists
                python -m venv mlip

                :: Activate venv and install packages
                call mlip\\Scripts\\activate
                pip install --upgrade pip
                pip install pytest numpy pandas scikit-learn

                :: Run pytest
                pytest

                :: Exit code will determine Jenkins build status
                '''
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                echo In this step, we deploy our project.
                echo Depending on the context, we may publish the project artifact or upload pickle files.
                '''
            }
        }
    }
}
