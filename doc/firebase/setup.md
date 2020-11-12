## Firebase Setup

Below are steps to setup you Google Firebase app and create a firebase library database object.

1. Head to [Google Firebase](https://firebase.google.com/). Click 'SIGN IN' at the upper right corner of the site.<br><br>
<img src="../images/step_1.png" width="600px" /><br><br>
2. You will need a Google account to create a Firebase account. Log into your Google account.<br><br>
<img src="../images/step_2.png" width="350px" /><br><br>
3. Click 'Go to console' in the upper right corner of the site.<br><br>
<img src="../images/step_3.png" width="600px" /><br><br>
4. Click 'CREATE NEW PROJECT' in the center of the page.<br><br>
<img src="../images/step_4.png" width="600px" /><br><br>
5. A modal window should pop up. Fill in the project name.<br><br>
<img src="../images/step_5.png" width="400px" /><br><br>
6. You should see this Firebase app dashboard. Click on the 'Add Firebase to your web app' icon.</br><br>
<img src="../images/step_6.png" width="600px" /><br><br>
7. Copy the API Key, Auth Domain, and Database URL from the highlighted areas. These three values are used in the firebase.loadFirebase function: `db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI', 'fir-docs-demo', 'fir-docs-demo')`.
<br><br>
<img src="../images/step_7.png" width="600px" /><br><br>
8. On the side panel of the Firebase app dashboard click the Database icon.<br><br>
<img src="../images/step_8.png" width="600px" /><br><br>
9. The dashboard shows three tabs for the Realtime Database. Click on the Rules tab.<br><br>
<img src="../images/step_9.png" width="600px" /><br><br>
10. The Firebase database Rules section is where rules to ensure security are set. For the basic setup the rules will be relaxed. <b>SECURE</b> your rules before sharing your firebase library based app. <br><br>
<img src="../images/step_10.png" width="600px" /><br><br>
11. Set the rules for ".read" and ".write" to "true" from "auth != null". <br><br>
<img src="../images/step_11.png" width="600px" /><br><br>
12. With the Firebase App setup done in the Python Mini add the following code:
```
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI', 'fir-docs-demo', 'fir-docs-demo')
```

The db variable now has the firebase object that is connected to the newly created app.
