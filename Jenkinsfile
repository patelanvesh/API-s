properties([parameters([choice(choices: ['qs03', 'qs04', 'qs05'], name: 'Environment'), choice(choices: ['Authenticated_Mobile_API-US', 'Authenticated_Mobile_API-CA', 'UnAuthenticated_Mobile_API-US', 'UnAuthenticated_Mobile_API-CA', 'TCAST-Invite-CA_Temp', 'TCAST-Invite-US_Temp'], name: 'Collection')])])

node {
   
          stage('Git cloning')
            {
              git url: "https://github.com/patelanvesh/API-s.git", branch : "master"
            }
            stage('Installing dependencies')
            {
              bat "npm install"
            }
            stage('Run tests')
            {
              bat 'npx newman run '+ "${params.Collection}"+'.postman_collection.json -e '+ "${params.Environment}"+'_Environment.postman_environment.json --reporters junit,cli,htmlextra --reporter-junit-export report.xml --reporter-htmlextra-export ./results/' +"${params.Collection}"+'.html'
              
            }
    }
