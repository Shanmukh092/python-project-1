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

				git fetch origin main:refs/remotes/origin/main feature:refs/remotes/origin/feature
				git checkout -B main origin/main

				git merge origin/feature --no-edit

				git push https://${GIT_USER}:${GIT_TOKEN}@github.com/Shanmukh092/python-project-1.git main
				'''
			}
		}
	}
	
}
