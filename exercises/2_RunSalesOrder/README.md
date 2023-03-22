## Table of Contents

- [Release business process project](#releaseproject)
- [Deploy released project](#deployproject)
- [Run business process](#businessprocess)
- [Monitoring the process flow](#processflow)
- [Accessing the tasks](#accessingtask)

# Step 1 <br>
## Release business process project <a name="releaseproject"></a>
<br>
To run the process you have to first release and then deploy the business process project.<br>

Releasing a project creates a version or snapshot of the changes and deploying the project makes it available in runtime to be consumed. You can only deploy a released version of the project, and at a given time there can be multiple deployed versions of the same project.<br> 
1. In the Process Builder, to release a project, choose the<b>Release</b> button on the top-right corner of the screen and provide a description.<br></br>
 <img src="./images/1.png"> <br> </br>

Version have x.y.z format where x is a major version number, y is minor and z is the patch number. Every time you release, a new version will be created. Version is incremented automatically based on how you want to store the changes in the repository like major or minor update or just as a patch. <br> </br>
<br>

2. If you are releasing for the first time, then the version will start with 1.0.0. Next time you release, the version numbers will be automatically updated.<br>
 <img src="./images/2.png"> <br> </br>

 # Step 2 <br>
## Deploy released project <a name="deployproject"></a>
<br>
1.Once the project is released successfully, you will find a <b>Deploy</b> option on the top-right corner of the screen.<br> <br> </br>
 <img src="./images/3.png"> <br> </br>
Click on <b> Next </b> for the all the subsequent screens as shown below.<br> </br>
 <img src="./images/4.png"> <br> </br>
 <img src="./images/5.png"> <br> </br>
Since we have created an <b>API trigger </b> in our process ,you can see <b>Sales Order Trigger</b> in the list of the triggers.<br> </br>
 <img src="./images/6.png"> <br> </br>
 Deploy will take a couple of seconds/minutes depending upon how big your project is and how many different artefacts it has. Any errors during the deployment will be shown in the Design Console. <br><br> </br>
 2. Once the deployment is successful, you will see a changed status. You can also see all your deployed and/or released project versions from the project status list next to the project name.
  <img src="./images/7.png"> <br> </br>
  You cannot edit released or deployed projects. To continue working on your project, you need to select the Editable option.<br> </br>
  You have successfully deployed your project. It is time to run the process and see the results.<br> </br>
  # Step 3 <br>
## Run business process <a name="businessprocess"></a>
<br>
1. Once you have successfully deployed the business process with an API trigger, you can view the API trigger in the Overview section under the tab Triggers. <br><br> </br>

Click View to see context of the workflow API.<br><br> </br>
  <img src="./images/8.png"> <br> </br>
 2. You can view the API URL and the payload to start the process.Copy the payload which would be used in the later steps .<br><br> </br>

Details of the payload: <br><br> </br>
<table>
  <tr>
    <th><b>Name</b></th>
    <th><b>Details</b></th>
  </tr>
  <tr>
    <td>definitionId</td>
    <td>ID of the process after it is deployed</td>
  </tr>
  <tr>
    <td>salesorderdetails</td>
    <td>Input parameter for the API trigger</td>
  </tr>
</table>
<br></br>
 <img src="./images/9.png"> <br> </br>

3. Since we have created API Trigger for the Business process ,let’s test the process with API Trigger in <b>Monitor</b> section before we start the process from SAP Build Apps.<br> </br>
<ul>
  <li>Navigate to <b>Monitor —> Manage —> Process and Workflow Definitions</b> .</li><br> </br>
  <li>Search for the project <b>Sales Order Management</b> that you have created.</li><br> </br>
  <li>Click on <b> Start New Instance</b>.</li><br> </br>
  <li>Paste the payload that you have copied in Step 2.</li><br> </br>
</ul>
<input text=" 1.  >> Don't modify the payload when you integrate with SAP Build Apps."><br> </br>

Since the Definition ID is already available in the Monitor section , remove the definition ID and context.<br><br> </br>
You payload should like below after providing values to the fields.<br><br> </br>
<textarea id="salesorderdetails" name="salesorderdetails" rows="4" cols="50"> { "salesorderdetails": { "material": "Laptop", "orderAmount": 900000, "shipToParty": "ABCD", "salesOrderType": "01", "salesOrganisation": "01", "distributionChannel": "01", "shippingCountry": "India", "expectedDeliveryDate": "2023-05-08", "division": "01" } } </textarea><br></br>
 <img src="./images/10.png"> <br> </br>
 <ul>
  <li>Click on <b>Start New Instance and Close</b>.</li><br></br>
</ul>

# Step 4 <br>
## Monitoring the process flow <a name="processflow"></a>
<br>
Monitoring business process is one of the key aspect of the automated processes. Technical monitoring is an administrator job where a process admin proactively and consistently monitors the process performance, identifies any issues in the process and takes necessary actions to ensure business process continuity.<br><br></br>
<b>SAP Build </b> provides different applications to monitor and manage different process artefacts. These applications are available under the <b>Monitor</b> tab.
<p>
1. All deployed processes can be accessed under Processes and Workflows under Manage. To monitor all the running instances of the process, you have to go to Monitor then <b>Process and Workflow Instances</b>.<br><br></br>
 <img src="./images/11.png"> <br><br> </br>
  
In there, you will see all the running, erroneous and suspended process instances. Use the filter bar to get a more customized view of the process instances based on different statutes like running, completed, suspended, terminated etc.<br> </br>

1. Choose your process instance that was just triggered above.<br> </br>
<input text=" Explore different process monitoring options. Observe the process instance information, process context which is the actual process data flowing across different activities in the process and the execution logs where you can see entire trace of how the process has been progressing with some basic runtime information of each activity."><br> </br>
 <img src="./images/12.png"> <br><br> </br>

 2. As you can see the process is waiting for the task to be completed. These tasks are generated from the forms that are added in the process and can be accessed via the<b> My Inbox</b> application.
 <img src="./images/13.png"> <br><br> </br>
  Notice the Recipients list. This is the same as configured in the General section of the Approval Form. The task will go into the inboxes of all the recipients. <br><br> </br>

  # Step 4 <br>
## Accessing the tasks <a name="accessingtask"></a>
<br>
1. Tasks are the request for the users to participate in an approval or review process. These tasks appear in the<b> My Inbox </b>application shipped with <b>SAP Build</b>. User can claim, approve and reject the task from their inbox.
<br><br> </br>
 <img src="./images/14.png"> <br><br> </br>
2. Once you <b>approve/reject </b>the approval task, <b>refresh</b> the inbox again to get the final notification based on action taken.<br><br> </br>
 <img src="./images/15.png"> <br><br> </br>
3. Once you acknowledge the notification sent via the approval process, the process will be completed.<br><br> </br>
<img src="./images/16.png"> <br><br> </br>



 




>>>>>>> Stashed changes
