node(appserver_3120_60)
def app
stage('Cloning Git')
{
    /* Lets make sure we have a repository to checkout SCM */

}

stage('Build-and_Tag')
{
    /* This build s the acutal image;
        * This is synonymous to docker  build on the command line */
    app.docker.build('charmsforschool/car_web')
}

stage('Post-to-dockerhub')
{
    docker.withRegistry('https://registry.hub.docker.com', '3ff81ca6-e73e-4a5e-969b-1c7b652f2a12')
}

stage('Deploy')
{
    sh "docker-compose down"
    sh "docker-compose up -d"
}