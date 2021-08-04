# Welcome to The Diabetic way
For full Website content visit [The Diabetic Way](https://www.thediabeticway.co.uk/index.php/en/).
<br>
<br>

## <span style="color:#111478">Setting up Atlas Account Part 3 </span> <br> 

<br>
<img width="auto" height="auto" border="0" align="center"  src="/img/Atlas/Robot face_ Atlas account_860x462.jpg" Setting up Atlas Part 3"/>

h) Add a database username (for example nightscout) and a database password (in the example below soo5ecret but please change it!).

<br>

Write down these credentials in the boxes below (yes, in this browser window you're reading now, unless you're reading a printed version). You’ll need them later.

<br>
Database password:<input type="text" id="myPwd" value="click here, delete and put your own " size="32">
<br>

Database username:<input type="text" id="myUsr" value="click here, delete and put your own" size="32">

<br>
Paste the string in the box below `(yes, in this browser window you're reading now, unless you're reading a printed version)`
<input type="text" id="myAtlas" value="click here, delete and paste your Atlas connection string" size="100">
<br>

Database Name: <input type="text" id="mydB" value="click here, delete and put your own" size="30">
<br>
Click the Generate button (just here below this line: in this browser window you're reading):

<br>


<button onclick="Generate()">Generate</button>




Field1: <input type="text" id="field1" value="Hello World!"><br>
Field2: <input type="text" id="field2"><br><br>
Field3: <input type="text" id="field3"><br><br>
<button onclick="myFunction()">Copy Text</button>

<p>A function is triggered when the button is clicked. The function copies the text from Field1 into Field2.</p>

<script>
function myFunction() {
  document.getElementById("field3").value = document.getElementById("field1","field2").value;
}
</script>





For full Website content visit [The Diabetic Way](https://www.thediabeticway.co.uk/index.php/en/).
<br>
<br>

## <span style="color:#111478">Setting up Atlas Account Part 3 </span> <br> 

<img width="auto" height="auto" border="0" align="center"  src="/img/Atlas/Robot face_ Atlas account_860x462.jpg" Setting up Atlas Part 3"/>



<font size="4">

This is a regular paragraph.

Paragraph:

1. **Now Open another tab**  to make a Mongodb Atlas** Account: <a href="https://www.mongodb.com/cloud/atlas" target="_blank" title="Click Start Free">See Here</a> 
  and **click** Start Free
 <img width="auto" height="auto" border="0" align="center"  src="/img/Atlas/MongoDB Atlas start free.jpg"Click Start"/>
      2. **No need to do this part** but I did.<img width="auto" height="auto" border="0" align="center"  src="/img/Atlas/MongoDB_Atlas account_setup.jpg"MongoDB Atlas Account Setup.jp"/>
 <br>
      3. Sub item three<br>
2. Item two


* Enter your information and then click Get Started Free
  <img width="auto" height="auto" border="0" align="center"  src="/img/Atlas/MongoDB Atlas fill in details2.jpg"Fill in your details"/>
  
  
  Select Create a cluster in Shared Clusters (FREE)
  
  
 
  
  Leave all default values and click Create Cluster
  
  
  
  
  
  Atlas will create your default cluster, wait until it is complete... (can take more than 3 minutes)
  
  
  
   Click on CONNECT
   
   
   f. Click on Allow Access from Anywhere
   
   
   Click on Add IP Address
   
   
   
   
   h) Add a database username (for example nightscout) and a database password (in the example below soo5ecret but please change it!).
   
   
   i) Then click Create Database User.
   
   
   j)Click on Choose a connection method
   
   
   Select Connect your application
   
   
   
   Copy the connection string: click Copy and paste it somewhere to edit it (like Notepad).
   
   
   
   
   
   
   p) If you want to do it manually: replace <password> with your database password as noted previously (in the example below soo5ecret) and <dbname> by any text you want, say mycgmic for example. The result will be like this:

mongodb+srv://nightscout:soo5ecret@cluster0.xxxxx.mongodb.net/mycgmic?retryWrites=true&w=majority
   
   
   
   
   
##Step 4: Fork and deploy cgm-remote-monitor
   
<br>   
   1.  You should now have 3 pages opened in your browser: Heroku, Atlas, and Github, Make sure you are logged-in on each one (i.e. not asking you to login) before you continue.
   
   2.  Click this link https://github.com/nightscout/cgm-remote-monitor, a new GitHub page will open. Click on Fork
   
   3. d) Scroll down and click Deploy to Heroku
   
   
   4. Enter your CGM in the Cloud site name: invent a name you will use to see your BG in the cloud. Confirm that the name is available.
   
   5.  Don’t change the region.
   
   6. Scroll down and setup the following variables:
   
   7. API_SECRET will be your Nightscout site password, it needs to be at least 12 characters long and you should NOT use spaces if you use @ or ! symbols remember you will probably need to express them using Percent encoding in your uploader and downloader apps. If you're not sure on how to do this, it is recommended to use only letters (uppercase + lowercase) and digits.
   
   8. If you want to link your Dexcom Share account as a data source, complete the following lines:
   
   9. If you want to link your CareLink account as a data source (currently not functional with Heroku), complete the following lines:
   
   10. Select the units you’re using in DISPLAY_UNITS acceptable choices are mg/dl or mmol/L (or just mmol).


11. In ENABLE, copy and paste the following words (separated by a space) so that won't have to think about which you want now:
12. Now you need the connection string you defined during the Atlas cluster creation (as the example below, but not the string below). Copy and paste it in the MONGODB_URI variable field.

If you compiled all the fields and successfully generated the string this is what you should copy in MONGODB_URI:

Sorry... something is missing for me to make it automatically...

13. If you preferred to make it yourself, make sure it looks like this:
mongodb+srv://nightscout:soo5ecret@cluster0.xxxxx.mongodb.net/mycgmic?retryWrites=true&w=majority


14. Scroll down to the end of the list and click Deploy app

15.  WAIT until completion (will take some time). Do not interrupt the process until it's complete.

16. Then click View (if nothing happens, click Manage App -> Open App, in upper right corner)

17. Your Nightscout site should open and direct you to a new profile creation.

18. Setup your Time zone and eventually all other fields. Do not leave any fields empty. If you don't know which value to use, just use the default value. You can change these values later at any time.

19. Browse down to Authentication status and click Authenticate. Enter your API secret. Click Update.


20. Click Save.

21.  If the following pop-up shows up click OK, and check status (upper right of the window).

22. If you need to modify your profile after this, authenticate with the lock icon (top right of the page): enter your API secret. Then click on the hamburger menu and select Profile Editor.

23. Dexcom Share and CareLink users should see data flowing in after some minutes. Other uploaders like xDrip+, Spike, xDrip4iOS, etc will need to be setup with the Nightscout address and API secret in the app.
   
   
   
   
</font>
 

Check what version you are upto on your Nightscout site. In my example I'm on version  14.06 (Liquorice)

<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><span style="color: #ffffff;">Note! video, see below</span></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">
<iframe width="850" height="415" src="https://www.youtube.com/embed/MFsbm45b6YY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  </span></td>
</tr>
</tbody>
</table>



Updating your website to the latest version
 <a href="https://github.com/nightscout/cgm-remote-monitor/releases" target="_blank" title="Nightscout Release Versions">See Here</a> for the 
 current released version at moment) is easy with the update tool linked below. 


 
## Instructions

These instruction have been made on the 28 <span style="background-color: #FFFF00">**April 2021**</span><br>
<br>
<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><strong><span style="color: #ffffff;">Note!</span></strong></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">Azure Users
as of 0.12, Nightscout no longer supports the free Azure platform now. If you really want to keep using Azure, don’t update to any version above 0.12</span></td>
</tr>
</tbody>
</table>
<br>

# Step 1 Update Github Repo

* Log into your GitHub Account.<a href="https://github.com/" target="_blank" title="GitHub Login">-- Here --</a>
<span style="background-color: #FFFF00">**Wait**</span>: Make sure you’re actually signed into your GitHub account and <span style="background-color: #FFFF00">**Check**</span> by looking in the upper right corner of the page to verify. You cannot do this later.<span style="background-color: #FFFF00">**Best to do it now!.**</span> 
😉 <br>

* Now<a href="http://nightscout.github.io/pages/update-fork/" target="_blank" title="Update Tool">-- Click Here --</a> to open the <span style="background-color: #FFFF00">**update tool or image below!**</span>for Nightscout in a new tab from Github. Make sure both are open<br>

* Enter your GitHub <span style="background-color: #FFFF00">**username**</span> and click the blue button that says Check for updates. (Note: your username is not an email address.)<br>


<a href="http://nightscout.github.io/pages/update-fork/" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/Time to Update Nightscout.png" title="Update Tool"/>
</a>
click the blue button that says<span style="background-color: #FFFF00">**Checks for updates**</span>

* If an update is available, the tool will tell you this,and provide directions for you, and also give you a button that will take you to <span style="background-color: #FFFF00">**GitHub**</span> to finish the process.

<a href="http://nightscout.github.io/pages/update-fork/" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/update availible.jpg" title="Update Tool"/></a><br>
  
* <span style="background-color: #FFFF00">**Click the Continue updating at GitHub button.**</span> Review the directions on the screen that pops up, and continue.

## step 1 `(see Step1 & Step2 video below)`

* <span style="background-color: #FFFF00">**Click "Create pull request"**</span> Your fork must be on the left side  
<a >
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/step1_creat_pull_request.jpg" title="Your fork must be on the left side and the nightscout/cgm-remote-monitor must be on the right. right."/></a>
 and the <span style="background-color: #FFFF00">**nightscout/cgm-remote-monitor must be on the right.**</span><br>
 
## step 2 create pull request

* Click <span style="background-color: #FFFF00">**"Create pull request” again,**</span> do not change the comparison. Your fork must be on the left side and the nightscout/cgm-remote-monitor must be on the right side.
<a >
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/step 2 create pull request again.jpg" title="Your fork must be on the left side and the nightscout/cgm-remote-monitor must be on the right. right."/></a>
* <span style="background-color: #FFFF00">** Also Give your pull request a name**</span> like “Update” or “Sweet Liquorice Update” — doesn’t really matter what this is.

## Step 1 & Step 2 Video
<br>


<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><span style="color: #ffffff;">step 1 & Step 2 Video</span></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">
<iframe width="850" height="415" src="https://www.youtube.com/embed/6tGsLOE1BuE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  </span></td>
</tr>
</tbody>
</table>


 <br>


## step 3 merge pull request

* Click <span style="background-color: #FFFF00">**"Merge pull request**</span>

<a >
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/step 3 merge pull request.jpg" title="Merge pull request"/></a>
  
* or see video below
<br>
<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><span style="color: #ffffff;">Note! video,</span></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">
<iframe width="850" height="415" src="https://www.youtube.com/embed/gUEqZAfPEZ4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  </span></td>
</tr>
</tbody>
</table>



## step 4 confirm merge
<br>
* Now Click the  <span style="background-color: #FFFF00">**Confirm merge button.**</span>
<a>
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/step 4 click  confirm merge.jpg" title="Step 4 Confirm Merge"/></a>

## step 5 merged

* If you see <span style="background-color: #FFFF00">**"Merged" in purple,**</span> you have successfully updated your fork. If you're using Heroku you will need to to push the Deploy Branch button, in the Manual deploy section of the Deploy page.

* <span style="background-color: #FFFF00">**You have successfully updated your GitHub repository**</span>, now let's deploy it in Heroku.
<br>
<br>
<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #db4e12;" fff=""><span style="font-size: 14pt;"><strong><span style="color: #ffffff;">Note!</span></strong></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">If you’re on Heroku and have Automatic Deploys enabled, you’re done!<br>
 If you don’t have Automatic Deploys on yet, or aren’t sure, run through these steps below!</span></td>
</tr>
</tbody>
</table>

# Step6: Deploy in Heroku
<br>

 
* Log into <a href="https://id.heroku.com/login" target="_blank" title="Nightscout Release Versions">Heroku</a>  
<a href="https://id.heroku.com/login" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Heroku/log into heroku.jpg" title="Log into Heroku"/>
</a>

* Select your app `(In my case The Dibetic Way)`
<img width="auto" height="auto" border="0" align="center"  src="/img/Heroku/Select_your_App.jpg" title="Select Deploy Tab"/>
<br>

* In the middle bit, click on the GitHub button if it isn’t already showing as connected. It will ask you to authorize the connection if you’re doing it for the first time.

<img width="auto" height="auto" border="0" align="center"  src="/img/Heroku/github connected.jpg" title="Select Deploy Tab"/>
<br>

* Type “cgm” into the repo-name search box, and click Search
<br>

* Click the Connect button once it finds your cgm-remote-monitor repository. You should now be connected
<br>

<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><span style="color: #ffffff;">Note! see video</span></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">
<iframe width="850" height="415" src="https://www.youtube.com/embed/5S2lcc5XY_g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  </span></td>
</tr>
</tbody>
</table>
  
* Or if Heroku is not connected to GitHub, scroll down and click Connect to GitHub, if a popup window opens and requires authorization, click Authorize Heroku
<br>
  
* Now after connecting to Gitnub, Scroll down to the bottom of the page, make sure to select the <span style="background-color: #FFFF00">master branch</span>  and then click <span style="background-color: #FFFF00"> Deploy Branch</span>
<br>
  <img width="auto" height="auto" border="0" align="center"  src="/img/Heroku/masterthendeploy.jpg" title="Select master then Deploy Branch"/>
</a>
<br>
* Build will start, do not interfere and wait for completion. It can take a while <span style="background-color: #FFFF00">approximately around 10 minutes Do not Interrupt the process</span>  has it can lead to a broken site and you'll need to restart again.
<br>  
  <img width="auto" height="auto" border="0" align="center"  src="/img/Heroku/Build-will-start.jpg" title="Build will start and information will scroll in the log window"/>
</a>
<br>
*  Wait until the deploy process completes and <span style="background-color: #FFFF00">click View</span> if nothing happens click Manage App then upper right Open App
<br>
  <img width="auto" height="auto" border="0" align="center"  src="/img/Heroku/view-App.jpg" title="Delect View now that the deploy process is complete"/></a>
<br>
*  Your site will open and  it should be at the latest version on your Nightscout Site
<br>
* <span style="background-color: #FFFF00">You're Finished!</span> 
* Head over to your Nightscout site and check its updated!


<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><span style="color: #ffffff;">Check if Nightscout as updated Video</span></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">
<iframe width="850" height="415" src="https://www.youtube.com/embed/MFsbm45b6YY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  </span></td>
</tr>
</tbody>
</table>
<br>

<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><span style="color: #ffffff;">Helpfull Note!</span></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">
<span style="background-color: #00000">To let your site finish updating itself as soon as you update your fork in the future with another Pull Request, enable Automatic Deploys here (from the master branch):
<br>                                                                </span> 

<iframe width="850" height="415" src="https://www.youtube.com/embed/x73tDH-ln4A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  <span style="background-color: #FFFFFF"> If you’ve just turned the Automatic thing on, you’ll need to manually do the first deploy — make sure the branch is on master, and click the Deploy Branch button:</span></td>
</tr>
</tbody>
</table>
<br>



<table width="1266" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #FF0000;" fff=""><span style="font-size: 14pt;"><strong><span style="color: #ffffff;">Warning!</span></strong></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;"> 1: Some new features, updates, or bug fixes may require that you clear your browser cache before you will see the changes taken effect<br/> 2: If you get no errors and no readings after a while see about doing a <a href="http://127.0.0.1:8000/user-guide/Redeploying%20your%20repository/" target="_blank" title="Redeploying your repository link">Redeploying your repository</a> </span></td>
</tr>
</tbody>
</table>
<br>
<a href="https://www.diabetes.org.uk/" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Diabetesuk/pngarea.com_rutgers-logo-png-8467605.png" title="Diabetes UK"/>
</a>               Why Not also visit [UK Wide Cycle Ride - Diabetes.uk](https://cycle.diabetes.org.uk/) for your Diabetes Needs! 


  <!--  
  
  mkdocs.yml    # The configuration file.
    docs/
    index.md  # The documentation homepage.
       ...       # Other markdown pages, images and other files.
		
		
		
<a href="http://nightscout.github.io/pages/update-fork/" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/Time to Update Nightscout.png" title="Update Tool"/></a>		
		
		
adding 	Yellow Hightligher!!!!!!!!	
<span style="background-color: #FFFF00">**Marked text**</span>


<a>
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/Time to Update Nightscout.png" title="Update Tool"/></a>	




Adding a image
<a href="https://www.youtube.com/watch?v=MFsbm45b6YY" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Nightscout/nightscout version_14.06.jpg" title="Version of Nightscout Video"/>
</a>


Adding Video

<iframe width="850" height="415" src="https://www.youtube.com/embed/MFsbm45b6YY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Note
**Note:** a note is something that needs to be mentioned but is apart from the context.


List
This is a regular paragraph.

Paragraph:

1. **Now Open another tab**  to make a Mongodb Atlas** Account: <a href="https://www.mongodb.com/cloud/atlas" target="_blank" title="Click Start Free">See Here</a> 
  and **click** Start Free
 <img width="auto" height="auto" border="0" align="center"  src="/img/Atlas/MongoDB Atlas start free.jpg"Click Start"/>
   2. Sub item two
   3. Sub item three
2. Item two



font size
<font size="4">

</font>



Table
| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |


-->

