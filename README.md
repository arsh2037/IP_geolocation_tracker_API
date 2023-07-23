# IP_geolocation_tracker_API

⚓ How I deployed the mule app to cloudHub:
    🔄Attempt 1: Using Mule Maven to deploy app to cloudHub2.0
        I thoroughly followed this doc:https://docs.mulesoft.com/mule-runtime/4.4/deploy-to-cloudhub-2 and dozens of associated docs along, and I created a design in my mind. 
        I configured the pom.xml file, .m2, settings.xml , installed JAVA and Maven set it up (env variables). 
        so the schema of the design I had in my mind is : Mule-maven -----publishes to----> Anypoint Exchange------> CloudHub2.0
        The maven commands I anticipated (and used) using: Firstly: mvn clean package deploy: It will deploy the app to Exchange 
        Then, use the command mvn clean package -DmuleDeploy. This should set my app in the shared space of cloudHub2.0

       :( However, there was some issue that I was not able to solve in the given time frame and this is the problem:
       [ERROR] Failed to execute goal org.mule.tools.maven:mule-maven-plugin:3.8.2:process-sources (default-process-sources) on project locateip: Execution default-process-sources of goal org.mule.tools.maven:mule-maven-plugin:3.8.2:process-sources failed: A required class was missing while executing org.mule.tools.maven:mule-maven-plugin:3.8.2:process-sources: org/eclipse/aether/connector/basic/BasicRepositoryConnectorFactory
       I tried deleting maven and re-installing it, ensuring I have the correct plugin with the right version but it didn't work. 

       Due to this, my pom.xml was not okay and I had to delete the whole project and remake it from scratch as it was not running nor was it able to manually deploy from "deploy to cloudHub" option in the studio

  👼Attempt 2: USing "Deploy to cloudHub" 
    I used this option and configured the requirements such as RAML version specifications and other stuff, finally was able to deploy this solution.

P.S.  
Currently this is the how the API looks in the anypoint platform: <br>
<img width="299" alt="image" src="https://github.com/arsh2037/IP_geolocation_tracker_API/assets/23148016/d011dd1c-d4b2-4919-8414-22d27afba9d5">

<strong>Note</strong>
<br>
when requesting access to the API : please select "10-req-policy"
<br>
<img width="253" alt="image" src="https://github.com/arsh2037/IP_geolocation_tracker_API/assets/23148016/ac6c4827-ca8d-4498-a0e0-77afa2bf2c18">


left To-DO: Use maven to deploy
