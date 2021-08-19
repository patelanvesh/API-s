node {
  
        stage('Git cloning')
        {
           git "https://github.com/patelanvesh/API-s.git"
        }
        stage('npm install dependencies')
        {
           bat "npm install"
        }
        stage('Run tests')
        {
           bat "npm run api-tests"
        }
    }
