# Microservices-based-Serverless-Application

-Deployed and provided API endpoints that will allow end users to find dealers for the products they want to buy. They can then find the rates offered by the dealers for each of these products and compare them to get an idea of competitive pricing.

-For this project, there will be two different repositories. One repository has the existing code for a Node.js application and a Python application. I deployed these applications on Code Engine and obtained a URL to access the API endpoints. Then I cloned another repository that will use these API endpoints and deploy the front-end application. Access the front-end application through the deployment URL, and I have showcased how seamlessly I have integrated the microservices into applications with screenshots for the final submission.

Deployed the Product Details Python application which provides API endpoints that can be used to get the products details by typing the below command:
-ibmcloud ce application create --name prodlist --image us.icr.io/${SN_ICR_NAMESPACE}/prodlist --registry-secret icr-secret --port 5000 --build-context-dir products_list --build-source https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
-View product_details_deploy.png

Deployed the Dealer Pricing Details Node.js application, which provides API endpoints that can be used to get the dealer pricing details by typing the below command:
-ibmcloud ce application create --name dealerdetails --image us.icr.io/${SN_ICR_NAMESPACE}/dealerdetails --registry-secret icr-secret --port 8080 --build-context-dir dealer_details --build-source https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
-View dealer_details_deploy

