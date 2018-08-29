# Isracard

1. The project has been developed with visual studio 2017 Community with the pluging for angular4 - the plugin can be download from visual studio extensions  - search it with the name : Angular CLI Templates .we need also that CLI has been installed on your machine 
we can open the folder of the Angular application through visual code also and debug from there but it is a better way from visual studio because we can debug client and server on the same instance .

2. Copy the Isracard solution in a dev folder from Here and extract the content all zip files near the solution file
3. Open the solution Isracard solution , and check that the project GitHub is running under .NET Core 2.0 , if you work with visual studio code it is irrelevant but you need to build the angular client with ng build or ng serve 
you need to do ng build manually in order all dependencies node_modules has been dowmload . you will see the folder under : 
GitHub\node_modules
compile the project NVC in order to download all dependencies for MVC .  all packages downloaded will be packages folder in solution folder.

4. For running application on chrome we need to install the plugin for cross origin support from url : 
   https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi
   otherwise we can't  execute  ajax call to MVC project server because we works different origin . 
   After the install we will see an icon in green color with content CORS- click on it to disable the plugin and click again to enable the plugin . that will solve the issue of the cross origin 

5. Solution structure : 
  5.1 -  GitHub - Angular CLI Project that contain a full angular4 application 
  5.2    GitHubServer -  MVC Project that hold on ASP.NET cache all the bookmarks done in Angular Client 
 
 6. User Information : 
 
    6.1 when we runs the application ,we will get a window with  a simple menu :  Repositories for doing searches and Bookmarks for displaying all the bookmarks existing in the system . 
    6.2 when we do searching , enter a string in the text box and click on search . we will see a galery of Images and under on each Image a button in shape of star .
    6.3 when we want to bookmark , we we click on the star button and if the operation succeeded , it will paint in yellow color . and we can't  click anymore on this image item . if the operation failed it will paint in red color and we can click again on the button to do a retry . 
    6.4 if we get an error Internal server , disable the plugin Cross origin and enabled it ( this issue is because we are in development environment ) 
    6.5 when we want to see the name of the repository , we will see a short string under the image - to see the original name move mouse on the text and we see the full name in a tooltip
    
  7. The Server has been developed that all the bookmarks has been saved in ASP.NET cache - in your request we ask to be save in the session on the server - ASP.NET sessions works that it save session ID in a cookie and each request we need to pass this cookie in the server for post requests 
  ajax call doe not know about such cookie , therefore in this case we can't work with ASP.NET session . this is the reason that i use the ASP.NET Cache with thread management 
  
  
