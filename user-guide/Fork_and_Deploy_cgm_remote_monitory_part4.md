# Welcome to The Diabetic way
For full Website content visit [The Diabetic Way](https://www.thediabeticway.co.uk/index.php/en/).
<br>
<br>

## <span style="color:#111478">Fork and Deploy cgm remote monitory Part 4 </span> <br> 

<br>
<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/Fork_and_Deploy_cgm_remote_monitory_Part_4t_860x462.jpg" Setting up Atlas Part 3"/>


   
<br>  
<font size="4"> 
1. Hopfully you should now have 3 pages opened in your browser: <span style="background-color: #FFFF00">**Heroku, Atlas, and Github,**</span> Make sure you are logged-in on each one (i.e. important) before you continue.

2.  <a href="https://github.com/nightscout/cgm-remote-monitor" target="_blank" title="Nightscout Release Versions">Click Here</a> or goto https://github.com/nightscout/cgm-remote-monitor, to open a new GitHub page. Click the on <span style="background-color: #FFFF00">**Fork**</span> icon in the top right
   <img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/1_fork.jpg"/>

3. Wait for a moment
  <img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/forking.jpg" title="WAIT until compleate"/>
</a>
   
3. Scroll down the page and click <span style="background-color: #FFFF00">**Deploy to Heroku**</span> 
   <img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/Deploy_to_Heroku.jpg"title="This deploys to Heroku Account"/>
   
4. Enter in your Heroku account a site name: invent a name you would like to use or see your BG in on the internet. Confirm that the name is available.
 <img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/site_name.jpg"title="Give yourself a App name"/>
 
5.  Don’t change the region.

6. <span style="background-color: #FFFF00">**Scroll down**</span> and setup the following variables: You can come back to these later later by going to settings and config Var!
<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/API_SECRET_Required2.jpg"title="Give yourself a API Secret Passwod"/>
     <iframe width="800" height="415" src="https://www.youtube.com/embed/65KI5-3E_XM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	 <table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #db4e12;" fff=""><span style="font-size: 14pt;"><strong><span style="color: #ffffff;">Note!</span></strong></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">The API_SECRET is the main password allowing full access to your Nightscout site. Make sure its secure (mix uppercase and lowercase letters, plus digits) and do no not share it publicly. If you think you exposed it by mistake, it is recommended that you change it.<br>
 If you don’t have Automatic Deploys on yet, or aren’t sure, run through these steps below!</span></td>
</tr>
</tbody>
</table>
7. <span style="background-color: #FFFF00">**API_SECRET**</span> will be your Nightscout site password, it needs to be at least 12 characters long and <span style="background-color: #FFFF00">**you should NOT use spaces if you use @ or ! symbolyou should NOT use spaces if you use @ or ! symbols**</span> remember you will probably need to express them using Percent encoding in your uploader and downloader apps. If you're not sure on how to do this, it is recommended to use only letters (uppercase + lowercase) and digits.
<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/API_SECRET_Required1.jpg"title="Give yourself a API Secret Passwod"/><br>
8. If you <span style="background-color: #FFFF00">**want to link your Dexcom Share account**</span> as a data source, complete the following lines:
<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/bridge_for_Dexcom_share.jpg"title=" Link your Dexcom Share Account "/><br>
<table width="1166" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="1" cellspacing="1" height="98">
<tbody>
<tr style="height: 16px;">
<td style="width: 1158px; border-color: #000000; background-color: #FF0000;" fff=""><span style="font-size: 14pt;"><strong><span style="color: #ffffff;">Warning!  Common Errors</span></strong></span></td>
</tr>
<tr style="height: 56.4063px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">MOST COMMON ERRORS

The BRIDGE_PASSWORD and BRIDGE_USER_NAME are NOT visible from within your Dexcom app or online account. These values are what you entered into your Dexcom mobile app when you logged into that app for the VERY FIRST time. The BRIDGE_USER_NAME is not an email address. The most common error on initial Nightscout setups is that people incorrectly use an old account or an old password. To test your username and password, go to Dexcom's Clarity page (check here <a href="https://clarity.dexcom.com/" target="_blank" title="Dexcom USA Account">See Here</a> for USA accounts and <a href="https://clarity.dexcom.eu/" target="_blank" title="Dexcom EU Account"> Here</a> here for the others) and try logging in to your Dexcom account. If your account info isn't valid, or you don't see any data in your Clarity account... you need to figure out your actual credentials before moving ahead.
</span></td>
</tr>
</tbody>
</table><br>
9. If you want to link your <span style="background-color: #FFFF00">**Care Link account**</span> as a data source (currently not functional with Heroku), complete the following lines:<br>
<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/mmconnect.jpg"title="Care Link Account"/>
<br>
10. Select the units you’re using in <span style="background-color: #FFFF00">**DISPLAY_UNITS**</span> the acceptable choices are <span style="background-color: #FFFF00">**mg/dl or mmol/L**</span> (or just <span style="background-color: #FFFF00">**mmol**</span> when entering it).
<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/display_units.jpg"title="Display Units"/><br>
In <span style="background-color: #FFFF00">**my case I used mmol**</span> <img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/display_unit_EU.jpg"title="Display Units"/><br>11. In <span style="background-color: #FFFF00">**ENABLE,**</span> copy and paste the following Plugins below <span style="background-color: #FFFF00">**(separated by a space)**</span> so that won't have to think about which you want now

| **Plugins**       |    |
| :------------- | |
|  careportal basal dbsize rawbg iob maker cob bwp cage iage sage boluscalc pushover treatmentnotify loop pump profile food openaps bage alexa override speech cors |
<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/enable.jpg"title="Plugins you can add to enable"/><br>

| **Plugins**       |    |
| :------------- | |
|  careportal basal dbsize rawbg iob maker cob bwp cage iage sage boluscalc pushover treatmentnotify loop pump profile food openaps bage alexa override speech cors |

<table width="1166" padding="0.35rem" border="1" style="border-color: #000000; background-color: #ffffff;" cellpadding="0" cellspacing="0" height="0">
<tbody>
<tr style="height: 0px;">
<td style="width: 1158px; border-color: #000000; background-color: #5B9BD5;" fff=""><span style="font-size: 14pt;"><strong><span style="color: #ffffff;">Enable Words</span></strong></span></td>
</tr>
<tr style="height: 0px;">
<td style="width: 1158px; border-color: #000000;"><span style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 14pt;">You find more information about the ENABLE on the: Nightscout Plugin Page <a href="http://127.0.0.1:8000/user-guide/Nightscout_Plugins/" target="_blank" title="Nightscout Plugin link">Here</a> </span></td>
</tr>
</tbody>
</table><br>
11. Now you need the <span style="background-color: #FFFF00">**connection string**</span> you defined during the <span style="background-color: #FFFF00">**Atlas cluster creation**</span> (as the example below, but not the string below). Copy and paste it in the MONGODB_URI variable field.<br>
ar 12. I will try to give you an example about the way to do it below:


<br>
   1. In the boxes below 1st is your Atlas Account you gave yourself a <span style="background-color: #FFFF00">**User Name**</span> add it to the box User Name
 <br>
   2. Then you made a <span style="background-color: #FFFF00">**Database Password add your Password** </span>you  created for your database
<br>
   3. And lastly you made a <span style="background-color: #FFFF00">**Database Name** </span>also add this to the last box and click the <span style="background-color: #FFFF00">**Copy Text button**</span>  which will generate your code that you will  need to add to your Heroku API
<br>
    <br>

</font>
<br><p>
<span style="background-color: #FFFF00">**username:**</span> <input type="text" id="username" value="click here, delete and put your own " size="32">  Eg username: <input type="text" id="egusername" value="Dave" size="32"><br>

<span style="background-color: #FFFF00">**Database password:**</span> <input type="text" id="dbpassword" value="click here,delete and put your own" size="31"> Eg Database password: <input type="text" id="egdbpassword" value="   Mypassword1234" size="20"><br>
<br>
<span style="background-color: #FFFF00">**Database Name:**</span> <input type="text" id="dbname" value="click here, delete and put your own " size="32"> E.g Database Name: <input type="text" id="egdbname" value=" Davesdatabase " size="20><br>output: <input type="text" id="output" value="click here, delete and put your own " size="32">
<br>
<br>
<p></p>


<br />
13. Yours should look simular to the one below mine might be a little different to what yours should be so do check it carefully<br>
 
<span style="background-color: #FFFF00">**mongodb+srv://**</span> <input type="text" id="field3"value="User Name">
: <input type="text" id="field4"value="Database Password">
@cluster0.lkqng.mongodb.net/ <input type="text" id="field5"value="Database Name">?retryWrites=true&w=majority<br><br>
<button onclick="myFunction()">Copy Text</button>



<script>
function myFunction() {
  document.getElementById("field3").value = document.getElementById("username").value;
  document.getElementById("field4").value = document.getElementById("dbpassword").value;
  document.getElementById("field5").value = document.getElementById("dbname").value;
  
}
</script><br>

13. In your connection string of Atlas: click Copy and paste your code somewhere to edit it (like Notepad)



<img width="auto" height="auto" border="0" align="center"  src="/img/Fork and Deploy cgm remote monitory Part 4/connecting_to_cluster.jpg" title="Version of Nightscout Video"/><br><br>

<a href="https://www.diabetes.org.uk/" target="_blank">
  <img width="auto" height="auto" border="0" align="center"  src="/img/Diabetesuk/pngarea.com_rutgers-logo-png-8467605.png" title="Diabetes UK"/>
</a>               Why Not take visit [UK Wide Cycle Ride - Diabetes.uk](https://cycle.diabetes.org.uk/) or  [Swim22 - Diabetes.uk](https://swim22.diabetes.org.uk/) for your Diabetes Needs!



   
   
</font>
 








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

