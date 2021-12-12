pipeline {
	agent any
	triggers {
		githubPush()
	}
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