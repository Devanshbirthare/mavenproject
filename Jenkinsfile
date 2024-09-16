pipeline 
{
    agent any

    stages
    {
        stage('scm checkout')
        {
            steps
            {
               git branch: 'master', url: 'https://github.com/Devanshbirthare/mavenproject.git' 

            }
        }

        stage('code compile')
        {
            steps
            {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
                {
                    sh 'mvn compile'
                }
            }
        }

<<<<<<< HEAD
    }
}
=======
   stage('code build')
 {steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true)  {
    sh 'mvn verify'
 } }}

 stage('deploy to tomcat server-Dev-Automated')
  {steps { sshagent(['deploy-to-tomcat']) 
   {
    sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.20.221:/usr/share/tomcat/webapps'

   } }}

 
  stage('deployment to Prod Manually') 
   { steps { sshagent(['deploy-to-tomcat']) 
    {
      input 'Do you approve deployment?'              // Conditional delivery
      sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.20.221:/usr/share/tomcat/webapps'
            }
      }
    }

}
}
>>>>>>> 5e77313ac3798e27b3f73ab8f65cb734cb418a6f
