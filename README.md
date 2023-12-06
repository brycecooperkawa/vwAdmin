# Volkswagen Shopping App with AR Admin Panel Github

# Description:
An admin panel that allows the admin to upload to, delete from, and edit models in the model database for the Volkswagen Shopping App with AR

# Details:
Upload vehicle allows the user to upload a model to the database  
Vehicle Name: name of the vehicle  
Vehicle Model URL: S3 link that directs to the model file  
Vehicle Website URL: link to the official vw website for the model of the car (uploading this through the admin panel, use tinyurl.com and upload the tinyurl for CORS error reasons  
Vehicle Image URL: link to an image of the vehicle  
Vehicle Colors: hexcodes for all colors available for the vehicle  
Vehicle Seat Positions: SIMD3 vectors to represent seat positions in the interior of the model, click add seat to add a seat, must have at least one  
Will not allow you to upload a model with an existing name

Upload accessory allows the user to upload an accessory model to the database  
Accessory Name: name of the accessory
Accessory URL: S3 link that directs to the model file 
Location: Location accessory will be displayed on the vehicles

Delete button removes the model from the database
**When using delete (or edit) if the table refreshes and delete hasn't gone through, inspect the webpage and look for 502 error**  
Found that at times of Amazon server error spikes, the call fails as Amazon is delivering it to the API  
Normally waiting for 15 minutes will solve this and the deletion will go through  
Check this website for aws info:  
https://downdetector.com/status/aws-amazon-web-services/  

Edit button allows the user to edit the model currently in the database  
**Since edit functions essentially as a delete and a new upload 502 errors can affect this too**  
Two cases of errors for edits:  
Either the edits won't go through, meaning the delete request failed  
Or the entry will delete and not reupload, meaning the upload request beat the delete request to the database  
Again, waiting 15-30 minutes normally resolves this problem  
We have found this error to be on Amazon's side  

Create account creates a user account that can be used in the application  

# Instructions to use:
index.html contains all html and js code  
styling is saved in the Styles.css code  
.glb file is used to model display  
if you want to set this up in a new github repository, follow the instructions linked here to set up the web page through github pages:  
https://docs.github.com/en/pages/quickstart  

# Login Information:
admin username: vw  
admin password: admin

# Web Page Information:
currently hosted on github pages under the url:  
https://brycecooperkawa.github.io/vwAdmin/  
with a stable internet connection and a viable web browser accessing the above url will display the admin panel  
will function like any other website plug in the index.html file as well as the Styles.css to wherever you would host  
the website and it should work

# Database stuff:
after the end of the 2023 fall semester, the databases this panel are connected to will likely be shut down  
if using after this, you probably need to adjust the links in the js code
