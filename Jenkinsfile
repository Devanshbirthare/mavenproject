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

        stage('execute unit test')
        {
            withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true)
             {
                sh 'mvn test'
             }

        }
    }
}
