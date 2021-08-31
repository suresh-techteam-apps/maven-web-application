node
{

def mavenHome = tool name: "maven3.8.2"
properties([[$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
stage('CheckoutCode')
{
git branch: 'development', credentialsId: '416c4c56-8528-4145-8dd3-d38c6bb7e688', url: 'https://github.com/suresh-techteam-apps/maven-web-application.git'
}
/*
stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
stage('ExecuteSonarcubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('uploadArtifactstoNexus')
{
sh "${mavenHome}/bin/mvn clean deploy"
}
stage('uploadArtifactstoNexus')
{
sshagent(['2f43c0a3-7fac-43f6-98df-ed10671bdbad']) {
 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.126.179.63:/opt/apache-tomcat-9.0.52/webapps/"

}
}
*/
stage('SendEmailNotification')
{
emailext body: '''Build Over...

Regards
Suresh Kumar K M
7019070589''', subject: 'Build over....', to: 'kmsuresh.devops@gmail.com'
}
}
