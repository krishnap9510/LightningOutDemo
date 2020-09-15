# Lightning-Out-Demo  
Follow the below steps to overcome the challenges mentioned above and to use your Lightning Components on external application (i.e. in our example is localhost). 



       Step 1: Generate X.509 Certificate using OpenSSL 

            First, you will have to install OpenSSL. After installing OpenSSL, generate a valid Self-Signed Certificate for localhost development.

        Step 2: Create Node.js application  

            First, install the Node Js library in your system.

Allow CORS in this application. 
Use SSL with this application.
        Step 3: Whitelists the localhost URL in CORS from Salesforce. 
            The Same-Origin-Policy restricts the browser to make a request to/from the same domain. 






      Step 4: Create a Connected App in Salesforce  
            From many ways to authenticate Salesforce from an external website, let's use the most secure way which is OAuth. To use OAuth, you need to create a Connected App. Connected App provides different types of permission settings to allow external websites to use after authentication. Do not forget to set the callback URL in your Connected App. 
 



 

      Step 5: Create Lightning Dependency App  

        To make this app accessible outside of Salesforce, make sure you do not forget the below points, 

The Lightning App must be globally accessible, which means that access must be defined as global. 
The ltng:outApp must be extended to allow you to use it outside the lightning framework / Salesforce. 
To make use of the Aura component as part of Lightning Out, it should be defined as aura:dependency. 

<aura:application access="Global" extends="ltng:outApp">
      <aura:dependency resource="c:LCSearchFirst" />     
      <aura:dependency resource="c:LCSearchDataTable"/>  
</aura:application> 


        Step 6: Include Lightning Out JavaScript 

            To use the Lightning component in your external application, you need to import Lightning             out JavaScript, so use the below resource in a script tag :    

https://your-domain.lightning.force.com/lightning/lightning.out.js 
