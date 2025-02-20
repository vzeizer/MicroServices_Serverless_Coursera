# MicroServices and Serverless from IBM Full-Stack Developer Certification

## Objectives:
After completing this lab, you will be able to:
1. Create an application consisting of multiple microservices.
2. Deploy Python and Node.js backend microservices on IBM Cloud Code Engine.
3. Deploy the frontend microservices on IBM Cloud Code Engine

### Deploying the Backend Microservices
1. Open the *Code Engine CLI*.
2. Deploy the microservice for Product Details, which provides API endpoints to retrieve product information.

- build-source - https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
- build-context-dir - products_list
- port - 5000
- ibmcloud ce application create --name prodlist --image us.icr.io/${SN_ICR_NAMESPACE}/prodlist --registry-secret icr-secret --port 50
- Copy the deployment URL and save it in a notepad or other text editors.

![logo](images/product_details_deploy.png)

3. Deploy the microservice for Dealer Pricing, which provides API endpoints to retrieve dealer pricing information.

- build-source - https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
- build-context-dir - dealer_details
- port - 8080
- name - dealerdetails
- image - us.icr.io/${SN_ICR_NAMESPACE}/dealerdetails
- Copy the deployment URL and save it in a notepad or other text editors.


![logo](images/dealer_details_deploy.png)

## Deploy the Frontend Microservice
1. Open new terminal, go to /home/project directory.

- cd /home/project

2. Clone the repository https://github.com/ibm-developer-skills-network/dealer_evaluation_frontend.git in your /home/project directory.

![logo](images/git_clone.png)

3. Change to the dealer_evaluation_frontend directory.
4. Update the index.html file with the deployment URLs obtained from the microservice deployments. (http://localhost:5000/ and
http://localhost:8080/), copy the deployment URLs you copied in the appropriate location. Make sure you end the URLs with a /.

![logo](images/index_urlchanges.png)

5. Deploy the Dealer Evaluation frontend microservice by pointing the build-source to the current directory.

- build-source - .
- port - 5001
- name - frontend
- image - us.icr.io/${SN_ICR_NAMESPACE}/frontend

![logo](images/frontend_deploy.png)

6. Click the link to load the homepage. Please note the page takes time to load the first time you access it.
7. Click the products drop down to see if the products have been populated.

![logo](images/homepage.png)

8. Choose a specific dealer for the product and verify the price is displayed.

![logo](images/product_dealer.png)

9. After the dealers dropdown populates, choose a particular dealer for the product and see if the price charged by that dealer is displayed.
- Allow 10 to 20 secs to load the page.

![logo](images/product_dealer_price.png)

10. Choose All Dealers option for a product (make sure you choose a product which has more than one dealer). Pricing of all dealers offering the product should
be shown on the screen.

![logo](images/product_all_dealers_prices.png)

## Summary:
In this lab, you've successfully deployed multiple microservices to build an integrated application. This includes two backend microservices, one developed in
Python and the other in Node.js, along with a front-end microservice.

