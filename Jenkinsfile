pipeline {
	agent any
	triggers {
		githubPush()
	}
	stages {
		stages('Test') {
			parallel {
				stage('Credit Tests') {
					steps {
						sh 'dotnet test --filter "FullyQualifiedName~CreditTests"'
					}
				}
				stage('Debit Tests') {
					steps {
						sh 'dotnet test --filter "FullyQualifiedName~DebitTests"'
					}
				}
			}
		}
	}
}