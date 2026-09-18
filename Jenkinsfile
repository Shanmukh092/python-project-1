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
				git checkout main
				git pull origin main
				git merge origin/feature
				git push origin main
				'''
			}
		}
	}
	
}
