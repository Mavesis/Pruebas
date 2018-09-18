pipeline {
  agent any
  stages {
      stage('CHECKOUT '){
        steps{
          echo'           ------------------------------------------------  COMENZANDO LA DESCARGA DEL PROYECTO  ------------------------------------------------                        '
          //git credentialsId: '6db993cd-816d-4ea0-96b0-2eb99685077d',
          git url: 'https://mavelazquez@bitbucket.org/ividevelopers/sw-dominios.git'
        }
      }
    //   stage('FASE 2 SMC '){
    //     steps{
    //       echo'           ------------------------------------------------  COMENZANDO LA CONSTRUCCIÓN DEL PROYECTO  ------------------------------------------------                        '
    //       bat 'mvn clean install'
    //       archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
    //     }
    //   }
      stage('ANALYSIS '){
        steps{
          echo'           ------------------------------------------------  COMENZANDO ANÁLISIS DEL PROYECTO   ------------------------------------------------                        '
          
          echo BRANCH_NAME

          withSonarQubeEnv('local_sonar'){
            
            bat 'C:/sonar-scanner/bin/sonar-scanner.bat -X -Dsonar.projectKey=ProyectoIvi -Dsonar.organization=Manuel Velázquez Sisternas -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=39acfca66c299343b8ac4427b69b5cb78db97cf1 -Dsonar.sources=. -Dsonar.language=js' //-Dsonar.branch.name='+BRANCH_NAME 
          }
        }
      }
  }
}

