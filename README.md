For this Enhancement I added MVC routes to "Rooms" and created a "Rooms" API endpoint to improve the data structure on the customer facing Express web application.
<br/>
<br/>
In this enhancement, the data structure will be enhanced by restructuring the customer facing rooms page to load the database dynamically instead of pulling information from the public static .html file. In doing so, the customer facing page will display changes made to rooms in the admin page. The rooms portion will be restructured in this enhancement by refactoring the code to use a MVC(Model, View, Controller) structure. Additionally, an API endpoint for localhost:3000/api/rooms will be added for testing purposes and easier compatibility with POSTMAN. Implementing the MVC structure for 'rooms' brings the project one step closer to completion as it integrates the database with both the admin page and the customer facing page. As is, the data for rooms was hard coded into the HTML file and the data was displayed in that way. Unfortunately, that setup is not practical for Travlr GetAways because the html code would need to be changed any time the admin team decided they wanted to add, edit, or delete a trip. Setting the rooms portion up to load the database dynamically to display real live data instead of hard-coded html data is crucial to meeting the client's requirements for the final project. 
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
