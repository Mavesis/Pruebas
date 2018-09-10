pipeline {
  agent any
  stages {
      stage('CHECKOUT '){
        steps{
          echo'           ------------------------------------------------  COMENZANDO LA DESCARGA DEL PROYECTO  ------------------------------------------------                        '
          git 'https://mavelazquez@bitbucket.org/ividevelopers/sw-dominios.git'
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
            
            bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar -Dsonar.projectKey=com.mycompany.app:my-app -Dsonar.organization=mavesis-github -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=39acfca66c299343b8ac4427b69b5cb78db97cf1 -Dsonar.branch.name='+BRANCH_NAME
          }
        }
      }
  }
}

