pipeline{
	agent any

	stages{
		stage("Build"){
			steps{
				sh 'python3 App.py'
			}
		}
		stage("merge"){
			steps{
				sh '''
				git config user.email "shanukh@local"
				git config user.name "Shanmukh"

				git fetch origin main feature
				git checkout -B main origin/main

				git merge origin/feature --no-edit

				git push origin main
				'''
			}
		}
	}
	
}
