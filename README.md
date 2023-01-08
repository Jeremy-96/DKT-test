# **DKT-test**

## **Introduction** 

Dkt-test is a simple web application in wich you can access a list of sports, sorting them thanks to a search-bar and view a description of one specific sport by clicking on it. All sports information can be found in the [Decathlon API](https://developers.decathlon.com/products/sports/docs).

<br>

## **Technologies**

*This application is created with the following technologies:*

<img src="https://user-images.githubusercontent.com/25181517/192158954-f88b5814-d510-4564-b285-dff7d6400dad.png" alt="HTML icon" style="width: 25px" />
<img src="https://user-images.githubusercontent.com/25181517/183898674-75a4a1b1-f960-4ea9-abcb-637170a00a75.png" alt="HTML icon" style="width: 25px" />
<img src="https://user-images.githubusercontent.com/25181517/117447155-6a868a00-af3d-11eb-9cfe-245df15c9f3f.png" alt="HTML icon" style="width: 25px" />
<img src="https://user-images.githubusercontent.com/25181517/121401671-49102800-c959-11eb-9f6f-74d49a5e1774.png" alt="HTML icon" style="width: 25px" />
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Svelte_Logo.svg/1200px-Svelte_Logo.svg.png" alt="HTML icon" style="width: 25px" />

*The mockup is made with :* 

<img src="https://user-images.githubusercontent.com/25181517/189715289-df3ee512-6eca-463f-a0f4-c10d94a06b2f.png" alt="HTML icon" style="width: 25px" />

*The web application is deployed with :*

<img src="https://logovtor.com/wp-content/uploads/2020/10/vercel-inc-logo-vector.png" alt="HTML icon" style="width: 50px" />

<br>

## **Getting started**  

Before starting, make sure to have Node.js installed locally on your device:
https://nodejs.org/fr/download/.
(For a better experience, choose the LTS version).

Now that you are ready to start, let's first clone the repository using the following command in your terminal:
```
git clone https://github.com/Jeremy-96/dkt-test.git
```  

Then go to the folder containing the code
```
cd dkt-test
```  

Install the packages that are needed to run the application 
```
npm install
```  

Finally, you can simply run the application using:
```
npm run dev
```   
<br>


## **Structure of the code**  

*Here, you can find a description of the main files that are used to create the application:*   

### **/public** 

* **global.css**  
In this file, global css properties can be added to the project (html, body, button ect...).

* **index.html**   
Make the application accessible in the web browser.

### **/src**

* **App.svelte**  
This file calls all components created in the application.  

* **Header.svelte**  
This file represents the header block. You can find it on the top of the page. In this component, a search-bar has been implemented to find a sport using its tag or its name. ***(Note: It's possible that a tag is not linked to any sport. In this case you will receive an error message. Feel free to try again with another tag.)*** 

* **SportsList.svelte**  
This component displays a list of all available sports in the Decathlon API. For each page, a maximum of twelve sports are shown. If you want to view more sports, feel free to go to another page by clicking on the page-btn at the bottom of the list.  

* **Sport.svelte**  
This component is used to access a specific sport from the SportsList component. By clicking on the "See more" link that appears on each sport's card, you can see the full description of a sport.


* **Footer.svelte**  
This file represents the footer block. You can find it at the bottom of the page.

**package.json**  
This file contains all dependencies used by the application.

<br>

## **Continuous deployment**  

The web application is continuously deployed using Github and [Vercel](https://vercel.com/).  

When a new version of the code is pushed to the main branch of the repository, Vercel automatically builds the application and deploys it on production. 


## **Sources**

* **[Node.js](https://nodejs.org/en/)**

* **[Svelte doc](https://svelte.dev/docs)**

* **[Decathlon API](https://developers.decathlon.com/products/sports/docs)**

* **[Vercel](https://vercel.com/)**  

