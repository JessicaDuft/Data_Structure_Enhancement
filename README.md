For this Enhancement I added MVC routes to "Rooms" and created a "Rooms" API endpoint to improve the data structure on the customer facing Express web application. I also implemented a sort by rate feature so that customers can sort rooms by rate in either ascending or descending order. This was implemented by adding two new endpoints titled "/SortUp" and "/SortDown" and then using MongoDB's built in sort() algorithm. 
<br/>
<br/>
In this enhancement, the data structure was enhanced by restructuring the customer facing rooms page to load the database dynamically instead of pulling information from the public static .html file. In doing so, the customer facing page will display changes made to rooms in the admin page. The rooms portion will be restructured in this enhancement by refactoring the code to use a MVC(Model, View, Controller) structure. Additionally, an API endpoint for localhost:3000/api/rooms will be added for testing purposes and easier compatibility with POSTMAN. Implementing the MVC structure for 'rooms' brings the project one step closer to completion as it integrates the database with both the admin page and the customer facing page. As is, the data for rooms was hard coded into the HTML file and the data was displayed in that way. Unfortunately, that setup is not practical for Travlr GetAways because the html code would need to be changed any time the admin team decided they wanted to add, edit, or delete a room. Setting the rooms portion up to load the database dynamically to display real live data instead of hard-coded html data is crucial to meeting the client's requirements for the final project. 
<br/>
<br/>
Prior to this enhancement, rooms loaded by pulling the static .html file in the public folder of our web application. Any changes made to rooms in the database would not appear on the customer facing page unless the same data was changed in the .html file.  The page was rendered like this : 
<br/>

<img width="468" alt="Picture6" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/e520b47d-7fb3-4e11-b36f-f6bd4b7ea137">

<br/>
<br/>

If a user attempted to navigate to localhost:3000/rooms the following page rendered : 
<br/>
<img width="468" alt="Picture7" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/af3d128d-e162-4289-970f-e38af09949ac">
<br/>
Now that the rooms data has been restructured to load dynamically using the MVC structure the following page renders : 
<br/>
<img width="468" alt="Picture8" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/a0b809c4-03c5-424a-8721-aaa72e813ea5">
<br/>
The data is now pulled from the MongoDB instead of the public .html file and data changes made on the admin site will be reflected on the customer site as well. 
<br/>
<br/>
Additionally, I also created an API endpoint for "Rooms" : 
<br/>

<img width="923" alt="Screenshot 2024-04-03 100855" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/6ca802a9-75dc-49ac-ba0f-3dec1f403491">
<br/>
<br/>

Additionally, I implemented a sorting feature on the Customer facing page that allows customers to sort rooms by rate in either ascending or descending order. To do this, I first created API endpoints for two new pages , “/SortUp” and “/SortDown”.  I then used MongoDB’s built in sort() algorithm to sort the rooms by rate in either ascending or descending order based on the way the user chooses to sort the rooms. If a user clicks sort price from lowest by highest, the web application will render rooms that were sorted using sort(asc) and will be rendered on a new web page that I have titled “SortUp”. The interface remains the same for a seamless user experience. If a user clicks sort price from highest to lowest, the web application will render rooms that were sorted using sort(desc) and will be rendered on a new web page that I have titled “SortDown”. Although a new web page is technically rendered, the user will not notice any difference on the web page itself other than the order that the rooms are sorted. The sort filter options looks like this : <br/>
<br/>
<br/>

<img width="337" alt="Picture14" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/db381dab-3e31-4efe-a035-d2d9a1d99a23">
<br/>
<br/>
<br/> 
If a user clicks “Lowest->Highest” the rooms will be rendered from lowest rate to highest rate. As shown below. Notice the URL has now changed to our new URL endpoint /SortUp 
</br>
<br/>
<br/>

<img width="468" alt="Picture15" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/d98afc3f-8830-454e-9f74-02b0a9df79e6">

<br/>
<br/>
<br/>

To render the SortUp page, I implemented the sort(asc) algorithm in the controller file that’s located in the App_Api folder (travlr\app_api\controllers\sortUp.js). See the function below : 
<br/>
<br/>
<br/>


<img width="468" alt="Picture16" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/c60bd46c-f6d4-4f9d-97c7-d4e1ade846c3">

<br/>
<br/>
<br/>
In a similar manner, the SortDown endpoint is rendered when a user chooses to sort from “Highest->Lowest”. When a user clicks “Highest->Lowest”, our new endpoint /SortDown is rendered and rooms are sorted from highest rate to lowest rate as seen below: 
<br/>
<br/>
<br/>
<img width="468" alt="Picture17" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/70ac23a8-5ec1-480a-9a1a-2f74b612748f">
<br/>
<br/>
<br/>
To sort the rooms from highest rate to lowest rate, I implemented MongoDB’s built in sort() algorithm in the SortDown controller that’s located in our App_Api folder (travlr\app_api\controllers\sortDown.js). See the function shown below : 
<br/>
<br/>
<br/>

<img width="468" alt="Picture18" src="https://github.com/JessicaDuft/Data_Structure_Enhancement/assets/130928718/9d6fb9b9-d86a-4051-acd4-907ea7d68d94">
<br/> 
<br/>
<br/>



For this enhancement the following folders and files were added or modified :

The following files were added in the app_api folder : 
[**\travlr\app_api\routes\rooms.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/routes/rooms.js)
<br/>

[**\travlr\app_api\controllers\rooms.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/controllers/rooms.js)
<br/>

[**\travlr_final\travlr\app_api\models\room.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/models/room.js)
<br/>

[**\travlr\app_api\controllers\sortUp.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/controllers/sortUp.js)
<br/>

[**\travlr\app_api\controllers\sortDown.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/controllers/sortDown.js)
<br/>

 [**\travlr\app_api\routes\sortUp.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/routes/sortUp.js)
 <br/>

[**\travlr\app_api\routes\sortDown.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/routes/sortDown.js)
<br/>


The following files were added or modified in the app_server folder: 
<br/>


[**\travlr\app_server\controllers\sortUp.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_server/controllers/sortUp.js)
<br/>

[**\travlr\app_server\controllers\sortDown.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_server/controllers/sortDown.js)
<br/>

[**\travlr\app_server\routes\sortUp.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_server/routes/sortUp.js)
<br/>

[**\travlr\app_server\routes\sortDown.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_server/routes/sortDown.js)
<br/>

[**\travlr\app_server\views\rooms.hbs**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_server/views/rooms.hbs) – Edited handlebars file to include the sort price option 
<br/>


Additionally lines 33-37, lines 58-62, and lines 73-78  were added in the [**\travlr\app.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app.js) file and lines 19-21 , and lines 49-88 were added in the [**\travlr\app_api\routes\index.js**](https://github.com/JessicaDuft/Data_Structure_Enhancement/blob/main/app_api/routes/index.js) file.





[**Return to EPortfolio**](https://github.com/JessicaDuft/CS499-Capstone)


