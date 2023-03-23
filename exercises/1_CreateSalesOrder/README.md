## Table of Contents

- [Create a business process project](#project)
- [Create a business process](#process)
- [Create an Data Type](#data)
- [Create and Configure Approval form](#aprrovalform)
- [Create and Configure Order Approval Notification form](#appnotification)
- [Create and configure Order Rejection Notification Form](#rejnotification)
- [Create and Configure Process Condition](#processcondi)
- [Create and Configure Auto Approval Notification](#autoapproval)
- [Save the Project](#save)

# Overview <a name="project"></a>


In this exercise, you will build your busines process to handle workflow approval.
This sample process includes the following:

1. An approval step to decide for approval or rejection of the sales order.

2. Confirmation and rejection forms to notify the requester about the decision.

3. Auto approaval based on sales order amount.

![Scenario](images/sap_build_architecture02.png)

# Step 1 <br>
## Create a business process project <a name="process"></a>

1. From [SAP Build Lobby](https://da160-96ork4sc-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby), click on <b>Create</b> and then select <b>Build Apps Project</b>.<br>

   | Username | Password    |
    | :------------- | :------------- |
    | AD160_XXX <br> where XXX is the user number <br> like AD160_000, AD160_001 etc.       | Acce$$teched22     |
    
<br><b>1.</b>In the <b>Lobby</b>, choose <b>Create</b>.<br><br>The lobby is a central page for creating, accessing, and managing your projects in SAP Build. You can access business application processes, company configured templates, and other resources for your end-to-end business process.has context menu.<br><br><img src="./images/1.png"><br>
<br><b>2.</b> Pick <b>build an Automated Process</b><br><img src="./images/2.png"><br>
<br><b>3.</b> Select <b>Buisness Process</b><br><br>Business Process Projects are a collection of skills in SAP Build Process Automation. Projects are part of the internal business processes of a company and are defined based on business scenarios. A project can contain a set of processes, forms, automations and decisions, which are reusable artifacts<br><img src="./images/3.png"><br>
<br><b>4.</b> In the <b>Create a Buisness Process</b> dialog box, do the following:<br>
<ul>
  <li>Enter a <b>Project Name:</b> Sales Orders Management.</li>
  <li>Enter a <b>Short Description:</b> Sales Orders Management Project.</li>
  <li>Choose <b>Create</b></li>
</ul><img src="./images/4.png"><br>

# Step 2 <br>
## Create a business process <br>

1. A new tab opens with the newly created project.<br>
2. In the <b>Create Process</b> dialog box, provide the following:
<ul>
  <li>Enter a  <b>Name: Order Processing</b></li>
  <li>Enter a <b>Description</b> for your process:A process to handle sales orders.</li>
  <li>Choose <b>Create</b></li>
</ul><br>
Inside a project, you can create a process. This process is equivalent to a workflow in any business scenario. You can create this process from different skills such as forms, decisions, automations.<br><br>
<img src="./images/5.png"><br>
The form <b>Identifier</b> field is auto-filled.

# Step 3 <br>
##  Create an Data Type

1. Click on +->**Create**–>**DataType** .<br><br>
<img src="./images/6.png"><br><br>
2. Create a datatype <b>Sales Order</b><br><br>
<img src="./images/7.png"><br><br>
3. Click on <b>New Field</b> to add new fields to the datatype <b>Sales Order.</b><br><br>
<img src="./images/8.png"><br><br>
4. Repeat the process to add all the fields of the type as shown below.<br>
<table>
  <tr>
    <th><b>Field Name</b></th>
    <th><b>Type</b></th>
  </tr>
  <tr>
    <td>material</td>
    <td>String</td>
  </tr>
  <tr>
    <td>orderAmount</td>
    <td>Number</td>
  </tr>
  <tr>
    <td>shipToParty</td>
    <td>String</td>
  </tr>
  <tr>
    <td>salesOrderType</td>
    <td>String</td>
  </tr>
  <tr>
    <td>salesOrganisation</td>
    <td>String</td>
  </tr>
  <tr>
    <td>distributionChannel</td>
    <td>String</td>
  </tr>
  <tr>
    <td>shippingCountry</td>
    <td>String</td>
  </tr>
  <tr>
    <td>expectedDeliveryDate</td>
    <td>Date</td>
  </tr>
  <tr>
    <td>division</td>
    <td>String</td>
  </tr>
</table><br>
  Your final data type looks as below.<br><br>
  <img src="./images/9.png"><br><br>

# Step 4 <br>
## Create and Configure API trigger
<br>
1. Click on <b>+–> API –> New API Trigger.</b><br><br><img src="./images/10.png"><br><br>
2. Enter the name as <b>Sales Order Trigger</b>.<br><br>
<img src="./images/11.png"><br><br>
3. Choose <b>Inputs</b>. Then choose <b>Configure</b> to configure inputs.<br><br>
<img src="./images/12.png"><br><br>
4. In the <b>Configure Process Inputs</b> window, choose <b>Add Input</b> to add parameters.<br><br>
Add the following parameter<br>
<table>
  <tr>
    <th><b>Name</b></th>
    <th><b>Type</b></th>
  </tr>
  <tr>
    <td>salesorderdetails</td>
    <td>SalesOrder</td>
  </tr>
</table><br><b>Apply</b> changes.<br><br>
<img src="./images/13.png"><br>
5.<b> Save</b> the project.<br>

# Step 5 <br>
## Create and Configure Approval form
<br><br>
1. Click on <b>+–> Approval–> New Approval Form.</b><br><br><img src="./images/14.png"><br><br>
2. Enter the name as <b>Approval Form.</b><br><br>
<img src="./images/15.png"><br><br>
3. Click on <b>Edit form.</b><img src="./images/16.png"><br><br>
4. Design the form by dragging and dropping the corresponding form elements as shown below.<br>
<table>
  <tr>
    <th><b>Form Fields</b></th>
    <th><b>Field Settings with label</b></th>
    <th><b>Configuration(Read Only)</b></th>
  </tr>
  <tr>
     <td>Approve Sales Order</td>
    <td>HeadLine1</td>
    <td></td>
  </tr>
  <tr>
     <td>A new order has been received.Please review and confirm whether the requirements canbe met or not.</td>
    <td>Paragraph</td>
    <td></td>
  </tr>
  <tr>
     <td>Material</td>
    <td>Text</td>
    <td>X</td>
  </tr>
  <tr>
     <td>Order Amount</td>
    <td>Number</td>
    <td>X</td>
  </tr>
  <tr>
     <td>Expected Delivery Date</td>
    <td>Date</td>
    <td>X</td>
  </tr>
  <tr>
     <td>I acknowledge that we have received your order and will process it based on the availability. </td>
    <td>Checkbox</td>
    <td></td>
  </tr>
  <tr>
     <td>Message to Buyer</td>
    <td>Text Area</td>
    <td>X</td>
  </tr>
</table><br>
<img src="./images/17.png"><br><br>
5. <b>Save</b> the form<br><br>
6. Click on the <b>Approval Form</b> and configure the <b>Subject</b> and <b>Recipients.</b><br>
<ul>
  <li>Enter <b>Please review</b></li>
  <li>Select <b>Material</b>from the sales order details</li>
</ul><br>
Enter your login credentials (emailID) in the <b>Recipients</b> section.<br>
<img src="./images/18.png"><br><br>
7. Configure the inputs of <b>Approval Form </b>.    Navigate to Inputs and map the fields accordingly.<br><img src="./images/19.png"><br><br>

# Step 6 <br>
## Create and Configure Order Approval Notification form
<br>
1. Click on +–>**Forms**–>**New Form**.<br><br>
<img src="./images/20.png"><br><br>
2. Enter the name as <b>Order Confirmation Form.</b><br><br><img src="./images/21.png"><br><br>
3. Click on <b>Edit form</b><br><br><img src="./images/22.png"><br><br>
4. Design the form by dragging and dropping the corresponding Form elements as shown below.<br>
<table>
  <tr>
    <th><b>Form Fields</b></th>
    <th><b>Field Settings with label</b></th>
    <th><b>Configuration(Read Only)</b></th>
  </tr>
  <tr>
     <td>Headline 1</td>
    <td>Order Confirmation</td>
    <td></td>
  </tr>
  <tr>
     <td>Paragraph</td>
    <td>our order has been received and accepted for delivery. We will send you the details as soon as the order is shipped. You can find the details of your order below, please review and verify your request:</td>
    <td></td>
  </tr>
  <tr>
     <td>Text Area</td>
    <td>Message from the supplier:</td>
    <td>X</td>
  </tr>
  <tr>
     <td>Text</td>
    <td>Material Name</td>
    <td>X</td>
  </tr>
  <tr>
     <td>Number</td>
    <td>Order Amount</td>
    <td>X</td>
  </tr>
  <tr>
     <td>Date</td>
    <td>Expected Delivery Date</td>
    <td>X</td>
  </tr>
  <tr>
     <td>Paragraph</td>
    <td>Please press the SUBMIT button to acknowledge the order status.</td>
    <td></td>
  </tr>
  </table><br><img src="./images/23.png"><br><br>
  5. <b>Save</b> the form.<br><br>
  6. Click on the <b>Order Approval Form</b> and configure the <b>Subject</b> and <b>Recipients.</b><br>
  <ul>
      <li>Enter <b>Your Order</b></li>
      <li>Select <b>Material</b>from the sales order details.</li>
      <li>Enter <b>has been approved.</b></li>
  </ul><br>
  Enter your login credentials (emailID) in the <b>Recipients</b> section.<br><img src="./images/24.png"><br><br>
  7. Configure the inputs of <b> Order Approval Form.</b> Navigate to Inputs and map the fields accordingly.<br><img src="./images/25.png"><br><br>



# Step 7<br>
## Create and Configure Order Rejection Notification Form<br><br>
1. To add the new rejection form, you will use the <b>Duplicate</b> feature. Select the <b>Overview.</b>
<ul>
      <li>Find <b>Order Confirmation Form</b>under the Artifacts section and select three dots (**…**).</li>
      <li>Choose <b>Duplicate</b></li>
  </ul>
<br><img src="./images/26.png"><br><br>
2. In the duplicate artifact pop-up window change the name to <b>Order Rejection Notification</b> and select <b>Duplicate</b>.<br>
<br><img src="./images/27.png"><br><br>
3. The form is automatically opened in the form builder. Change the order rejection form in the form builder to reflect the data for rejection case.<br><br>
<table>
  <tr>
    <th><b>Form Fields</b></th>
    <th><b>Field Settings with label</b></th>
  </tr>
  <tr>
    <td>Headline 1</td>
    <td>Order Rejection</td>
  </tr>
   <tr>
     <td>Paragraph</td>
    <td>We are sorry to inform you that your order cannot be accepted. Any inconvenience caused due to the refusal of the order is regretted. You can find the reason of the rejection and the details of your order below, please confirm the request:</td>
  </tr></table><br><img src="./images/28.png"><br><br>
  4. <b>Save</b> the form.<br>
  5. Go back to the process builder and add the order rejection notification form to the process. Select <b>Approval Form</b> and choose + option for the <b>Reject.</b> Choose <b>Forms</b> and select <b>Order Rejection Form.</b>
<br><img src="./images/29.png"><br><br>
  6. Configure the order rejection form. In the General section configure in the <b>Subject</b> box:<br>
  <ul>
      <li>Enter <b>Your Order</b> </li>
      <li>Select <b>Order Number</b> from the Order Processing Form</li>
      <li>Enter <b>is rejected by the supplier</b></li>
  </ul><br>
  7. Under Recipients Enter your login credentials(emailID)<br><br><img src="./images/30.png"><br><br>
  8. Configure the <b>Inputs</b><br> section.<br>
  <table>
  <tr>
    <th><b>Form Input Fields</b></th>
    <th><b>Process Content Entry</b></th>
  </tr>
  <tr>
    <td>Expected Delivery Date</td>
    <td>Expected Delivery Date</td>
  </tr>
  <tr>
    <td>Message from the supplier</td>
    <td>Message to buyer</td>
  </tr>
  <tr>
    <td>Order Amount</td>
    <td>Order Amount</td>
  </tr>
  <tr>
    <td>Material Name</td>
    <td>Material Name</td>
  </tr>
  </table><br>
  <br><img src="./images/31.png"><br><br>
  9. Finally, connect the outgoing flow of the order rejection form to the <b>End</b> activity.<br>
  <br><img src="./images/32.png"><br><br>
  10. <b>Save</b> your work.<br>
     With this you have completed the process design of your business process. You have experienced building a process in a completely no-code environment and with no technical know-how. You used the process builder to create a one-step approval process with the API trigger , approval form and notification forms.<br><br>

# Step 8<br>
## Create and Configure Process Condition<br><br>
Once the process with forms is designed, define which process flow should run based on if/else condition criteria.<br>
1. To add a condition to a process open the <b>Process Builder</b>. Choose + next to the Trigger. Select <b>Controls</b> then <b>Condition.</b><br><br><img src="./images/33.png"><br><br>
2. To configure the condition, choose <b>Open Condition Editor.</b><br><br><img src="./images/34.png"><br>Process content will contain a list of attributes that have been defined in previous skills. For example: in the screenshot, you can see attributes from the API trigger . You will use this process content to configure different skills during business process modelling.<br>
3.  Edit your branch condition:<br>
<ul>
  <li>Set <b>Order Amount</b>from the process content</li>
  <li>Select is <b>less than</b></li>
  <li>Enter <b> 100000</b>as the value</li>
  <li>Choose <b>Apply</b></li>
</ul><br><img src="./images/35.png"><br><br>
You have configured your <b>if</b> branch to: <b>if Order Amount is less than 100000.</b><br><br>
4. Link your <b>Default</b> branch to <b>Approval Form.</b>
<br><img src="./images/36.png"><br><br>
With this process condition, only the sales order above a specific amount will be sent for approval and the rest will be auto-approved.<br><br>
5. Decide the process flow if the condition criteria is met. First, you have to remove the connection from If-route to Approval Form and then create a new form to notify the requester of the auto-approval.
<br><img src="./images/37.png"><br><br>

# Step 9<br>
## Create and Configure Auto Approval Notification<br><br>

1. To create the new form, add the <b>New Form</b> from the <b>If-route.</b><br><br><img src="./images/38.png"><br><br>
2. In the Create Form window:<br>
<ul>
  <li>Enter the Name:<b> Auto Approval Notification</b></li>
  <li>Enter a Description: <b>Notification form to inform auto approval of the sales order.</b></li>
  <li>Choose <b>Create</b></li>
</ul><br><img src="./images/39.png"><br><br>
3. Edit the form using <b>Edit Form</b> Button .Design the notification form, the same way as in the previous steps, to send another notification to the requester about auto-approval.Add <b>Layout fields:</b><br><br>
<table>
  <tr>
    <th><b>Form Fields</b></th>
    <th><b>Field Settings with label</b></th>
    <th><b>Configuration (Read Only)</b></th>
  </tr>
  <tr>
     <td>Headline 1</td>
    <td>Automatic Order Confirmation</td>
     <td></td>
  </tr>
  <tr>
     <td>Paragraph</td>
    <td>Your order has been received and we will send you the details as soon as the order is shipped. You can find the details of your order below, please review and verify your request:</td>
     <td></td>
  </tr>
   <tr>
     <td>Paragraph</td>
    <td>Your Sale’s Order Details:</td>
     <td></td>
  </tr>
   <tr>
     <td>text</td>
    <td>Material Name</td>
     <td>X</td>
  </tr>
   <tr>
     <td>Number</td>
    <td>Order Amount</td>
     <td>X</td>
  </tr>
   <tr>
     <td>Date</td>
    <td>Expected Delivery Date</td>
     <td>X</td>
  </tr>
   <tr>
     <td>Paragraph</td>
    <td>Please press the SUBMIT button to acknowledge the order status</td>
     <td></td>
  </tr>
  </table><br>
  <img src="./images/40.png"><br><br>
  4. <b>Save</b> your work.<br><br>
  5. Go back to the process builder and configure the auto approval form.<br>
  6. Configure the <b>General section</b>. Under Subject:
  <ul>
  <li>Enter: Your order</li>
  <li>Choose:<b>Order Number</b> from Order Processing Form</li>
  <li>Enter:<b>has been successfully received</b> </li>
</ul><br>
   Under Recipients Enter your login credentials (emailID)<br>
  <img src="./images/41.png"><br><br>
  7. Configure the <b>Inputs</b> section.<br>
<table>
  <tr>
    <th><b>Form Input Fields</b></th>
    <th><b>Process Content Entry</b></th>
  </tr>
  <tr>
     <td>Material Name</td>
    <td>Material Name</td>
  </tr>
   <tr>
     <td>Order Amount/td>
    <td>Order Amount</td>
  </tr>
   <tr>
     <td>Expected Delivery Date</td>
    <td>Expected Delivery Date</td>
  </tr>
  </table>
 <br><img src="./images/42.png"><br><br> 
 8. Connect the outgoing flow of the auto-approval form to the <b>End</b> activity.<br><br><img src="./images/43.png"><br><br> 

# Step 10<br>
## Save the Project<br><br>
   
<b>Save</b> your work.<br>

This completes the process design with condition criteria that will decide what process flow is executed and whether there will be an auto-approval or a one-step approval route.<br>






























