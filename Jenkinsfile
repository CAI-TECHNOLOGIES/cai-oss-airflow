pipeline
{
    agent any
    stages
    {
         stage('Clone repository')
             {
                steps
                {
                   script
                   {
                      checkout scm
                   }
                }
            }

        stage('Build')
        {
            steps
            {
                script
                {
                    app = docker.build("oss-airflow:test")
                }
            }
        }
/*
        stage('Deploy Dev')
        {
            steps
            {
                script
                {
                    withCredentials([file(credentialsId: 'financial-intelligence-vars', variable: 'vars_data')])
                    {
                        sh "cp $vars_data env"
                        sh "docker-compose down"
                        sh "docker-compose up -d"
                        sh "rm env"
                        sh "/app/nginx_deployment/setup_nginx.sh"
                    }
                }
            }
        }
*/
    }
}
