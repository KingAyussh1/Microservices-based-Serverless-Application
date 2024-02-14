# Microservices-based-Serverless-Application

-Deployed and provided API endpoints that will allow end users to find dealers for the products they want to buy. They can then find the rates offered by the dealers for each of these products and compare them to get an idea of competitive pricing.

-For this project, there will be two different repositories. One repository has the existing code for a Node.js application and a Python application. I deployed these applications on Code Engine and obtained a URL to access the API endpoints. Then I cloned another repository that will use these API endpoints and deploy the front-end application. Access the front-end application through the deployment URL, and I have showcased how seamlessly I have integrated the microservices into applications with screenshots for the final submission.

1) Deployed the Product Details Python application which provides API endpoints that can be used to get the products details by typing the below command:
- ibmcloud ce application create --name prodlist --image us.icr.io/${SN_ICR_NAMESPACE}/prodlist --registry-secret icr-secret --port 5000 --build-context-dir products_list --build-source https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
- View product_details_deploy.png

2) Deployed the Dealer Pricing Details Node.js application, which provides API endpoints that can be used to get the dealer pricing details by typing the below command:
- ibmcloud ce application create --name dealerdetails --image us.icr.io/${SN_ICR_NAMESPACE}/dealerdetails --registry-secret icr-secret --port 8080 --build-context-dir dealer_details --build-source https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
- View dealer_details_deploy.png

3) Cloned the repository - https://github.com/ibm-developer-skills-network/dealer_evaluation_frontend.git
- View git_clone.png

4) Deployed the frontend application by pointing the build source to the current directory by typing the below command:
- ibmcloud ce application create --name frontend --image us.icr.io/${SN_ICR_NAMESPACE}/frontend --registry-secret icr-secret --port 5001 --build-source .
- View frontend_deploy.png
- Click the link to load the homepage.

5) Click the products drop-down to see if the products have been populated.
- View homepage.png

6) After selecting the product from the dropdown, the dealers that supply the product should be displayed.
- View product_dealer.png

7) After the dealers dropdown populates, choose a particular dealer for the product and see if the price charged by that dealer is displayed.
- View product_dealer_price.png

8) Choose the All Dealers option for a product (make sure you choose a product that has more than one dealer). Pricing of all dealers offering the product should be shown on the screen.
- View product_all_dealers_prices.png

Finally, I have created two backend applications to be used as microservices on Code Engine and deployed one front-end application that uses the microservices.
