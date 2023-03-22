<<<<<<< Updated upstream
### Table of Contents
- [Create a SAP BUid App](#project)
- [Create a business process](#process)
- [Create an Data Type](#data)
- [Create and Configure Approval form](#aprrovalform)
- [Create and Configure Order Approval Notification form](#appnotification)
- [Create and configure Order Rejection Notification Form](#rejnotification)
- [Create and Configure Process Condition](#processcondi)
- [Create and Configure Auto Approval Notification](#autoapproval)
- [Save the Project](#save)

<<<<<<< Updated upstream
# Overview <a name="project"></a>


In this exercise, you will build your app in SAP Build Apps to upload invoice.
=======
## Table of Contents
- [Create a business process projects](#project)
- [Create a business process](#process)
- [Create an Data Type](#data)
- [Create and Configure Approval form](#aprrovalform)
- [Create and Configure Order Approval Notification form](#appnotification)
- [Create and configure Order Rejection Notification Form](#rejnotification)
- [Create and Configure Process Condition](#processcondi)
- [Create and Configure Auto Approval Notification](#autoapproval)
- [Save the Project](#save)

# Overview <a name="project"></a>


In this exercise, you will build your app in SAP Build Apps to upload invoices.

![Scenario](images/scenario_appgyver.png)


## Create a business process project <a name="process"></a>

1. From [SAP Build Lobby](https://da160-96ork4sc-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby), click on <b>Create</b> and then select <b>Build Apps Project</b>.<br>

   | Username | Password    |
    | :------------- | :------------- |
    | AD160_XXX <br> where XXX is the user number <br> like AD160_000, AD160_001 etc.       | Acce$$teched22     |
    
<br>![Create the project](images/01a.png)
<br>![Create the project](images/01b.png)

2. Under <b>Project Name</b>, enter <b><i>"Invoice AD160-XXX"</b></i>, replace XXX with your user ID. For example, <i>"Invoice AD160-087"</i>.<br>Click on <b>Create</b> to start building your application.
<br><br>![Name the project](images/01c.png)


## Create UI <a name="data"></a>

1. You will be redirected to <b>Build Apps Composer</b>, which is like an IDE for SAP Build Apps. On the canvas, you can already see a <b>Title</b> and a <b>Text</b> component.<br><br>![home page](images/01.png)

2. Click on “<i>Headline</i>” on the canvas to select the <b>Title</b> component.
Now, the <b>PROPERTIES</b> tab on the right-hand side will show the properties of the <b>Title</b> component where you can modify it.<br> Under <b>Content</b>, enter “<i>Invoice Approval.</i>”<br><br>![Title component](images/02%202.png)

3. Select the <b>Text</b> component, modify the <b>Content</b> under the <b>PROPERTIES</b> tab on the right-hand side to "<i>Enter your name and upload your invoice</i>".<br><br>![text component](images/03.png)

4. Drag and drop an <b>Input field</b> from the <b>UI Component</b> library into the canvas. <br><br>![input component](images/04.png)

5. Under the <b>PROPERTIES</b> tab of the <b>Input field</b>, clear the <b>Label</b> and change the <b>Placeholder text</b> to "<i>Enter your name</i>".<br><br>![input properties](images/05.png)

6. Drag and drop a <b>Button</b> component from the component library on the left-hand side into the canvas. <br>Change the <b>Label</b> on the button in the <b>PROPERTIES</b> tab of the button component to “<i>Upload your Invoice</i>”.<br><br>![Button](images/06.png)

7. Drag and drop an <b>Image</b> component into the canvas.<br><br>
![Image](images/07.png)

8. Switch to <b>VARIABLES</b> view.

    > In <b>Variables view</b>, you can create variables which can store information temporarily.

    ![Variables](images/08.png)

9. Create an <b>App variable</b> by clicking on <b>ADD APP VARIABLE</b> and rename it to "<i>name</i>".<br><br>
![create variable](images/09.png)

10. Add another <b>App variable</b> and rename it to "<i>Invoicescan</i>".<br><br>
![create another variable](images/10.png)

11. Change the <b>Variable value type</b> of <b>Invoicescan</b> to <b>Local filesystem path</b>.<br><br>
![variable type](images/11.png)

12. Add another <b>App variable</b> and rename it to <b>filename</b>.<br><br>
![variable type](images/71.png)

13. Switch back to <b>VIEW</b>. <br><br>
![View](images/VIEW.png)

14. Under the <b>PROPERTIES</b> tab of the <b>Input field</b> component, open the binding menu for <b>Value</b> by clicking on the "<b>X</b>" icon.<br><br>
![bind menu](images/13.png)

15. The binding menu will pop-up. Select <b> Data and Variables</b>.<br><br>![binding menu ](images/14.png)

16. Select <b>App variable</b>.<br><br>
![app variable inbind menu](images/15.png)

17. Select <b>name</b> in the list of <b>App variable</b> available.<br><br>
![name of app vairble](images/16.png)

18. Click on the <b>SAVE</b> button to save the binding to the component value.<br><br>
![SAVE button](images/17.png)

19. A variable can be binded to this image component. Open the binding menu of the <b>Image</b> component under <b>PROPERTIES</b> on the right-hand side.<br><br>
![bind menu](images/18.png)

20. The binding menu will pop-up. Select <b>Data and Variables</b>.<br><br>
![bind image](images/19.png)

21. Select <b>App variable</b>.<br><br>
![app variables](images/20.png)

22. Select <b>Invoicescan</b> under the list of available app variables and click on <b>SAVE</b> to save the binding to the <b>Image</b> component.<br><br>
![variable](images/21.png)

23. Drag and drop another <b>Button</b> component from the component library into the canvas and rename the <b>Label</b> to <i>Submit</i>.<br><br>
![Submit ](images/22.png)

24. The <b>Submit</b> button should be visible only after the invoice is selected. Click on <b>ADVANCED PROPERTIES</b> to change the visibility properties of the button. Open the binding menu for the visibility properties.<br><br>
![](images/23.png)

25. Select <b>Formula</b>.<br><br>
![](images/24.png)

26. In the formula bar enter the following formula:

    <pre>IF(IS_EMPTY(appVars.Invoicescan),false,true)</pre>

    > This formula checks if the <b>InvoiceScan</b> page variable is empty, then the output will be false and component will be disabled. If the <b>InvoiceScan</b> page variable has some value, the output will change to true, and the component will be displayed.

    Click on <b>SAVE</b>.

    ![](images/25.png)

26. Click on <b>SAVE</b>.<br><br>
![](images/26.png)

27. Click on <b>SAVE</b> on the top right corner to save the UI created so far.<br><br>
![](images/27.png)

## Data Connection <a name="aprrovalform"></a>

Now, your application will be connected to Document Management System and SAP Process Automation. First, you should enable BTP authentication to connect your app to SAP Process Automation via Destinations.

1. Choose <b>AUTH</b> tab on the top of the screen.<br><br>
![](images/36.png)

2. Select <b>ENABLE AUTHENTICATION</b>.<br><br>
![](images/37.png)

3. Select <b>SAP BTP authentication</b>.<br><br>
![](images/38.png)

4. Click on the <b>OK</b> button to enable the BTP authentication to your application. <br><br>
![](images/39.png)

5. Click on <b>DATA</b> tab.<br><br>
![](images/40.png)

6. Under <b>SAP AppGyver classic data entities</b>, click on <b>CREATE DATA ENTITY</b> and select <b>SAP BTP destination REST API integration</b>.<br><br>
![](images/41.png)

7. As the <b>BTP destination name</b>, select <b>AppGyver_SPA</b>.<br><br>
![](images/Destination.png)

8.  Under <b> Data resource name</b>, a name can be given to this data connection, like "<i>SendtoSPA</i>".<br><br>
![](images/43.png)

9. Under <b>Resource schema</b>, click on <b>+ ADD NEW</b> to create a schema. Name the new schema to "<i>filename</i>" and select the <b>Field type</b> as <b>Text</b>.
Choose <b>ADD.</b>

    > Schema is structure of the data. A schema is created which is similar to the Data base. In this scenario the data base is Document Management System (DMS), and schema should be created matching the schema in DMS.

    ![](images/44.png)<br><br>

10. Similarly, add three other schema with the following names:
  - "<i>foldername</i>"
  - "<i>employeename</i>"
  - "<i>employeemail</i>"

    Select the <b>Field type</b> for all of them as <b>Text</b>.<br><br>
    ![](images/newdata.png)

11. Select the <b>create</b> tab, and enable it.<br><br>
![](images/46.png)

12. Open the binding menu for <b>Request headers</b> by clicking on the <b>X</b> icon.<br><br>
![](images/47.png)

13. In the binding menu, select <b>List of values</b>.<br><br>
![](images/48.png)

14. Click on <b>Add value</b>, and enter the following values:
    - <b>Header name</b>: <i> Content-Type</i><br>
    - <b>Header value</b>:<i> application/json</i>

    Click on <b>SAVE</b>.

    ![](images/49.png)

15. <b>Request body mapper</b> value will be binded after creating the process using SAP BUILD PROCESS AUTOMATION.

    Click on <b>SAVE DATA RESOURCE</b>. The connection between your Application and Process is created using Destinations. <br><br>
    ![](images/53.png)


16. Add another data entity to store the invoice in Document Management Service.
    > For this data connection, Destinations are not used because, the response from Document Management Service is in XML format. AppGyver can only read JSON responses.<br> Because of this reason Document Management Service is connected using DIRECT REST API.

    Click on <b> CREATE DATA ENTITY</b> and now select <b>REST API direct integration</b>.

    ![](images/54.png)<br><br>

17. In the <b>BASE</b> tab of the API configuration enter the following values:
  - <b>Resource ID</b> : Documentupload
  - <b>Resource URL</b>: https://end-to-end-demo-lcnc-trial.integrationsuitetrial-apim.eu10.hana.ondemand.com/end-to-end-demo-lcnc/httpjsonv2/docrepouploadteched
  <br><br>

    ![](images/55.png)

18. Select the <b>CREATE RECORD</b> tab and enable it.<br><br>
![](images/56.png)

19. Switch to the <b>SCHEMA</b> tab.<br>
 Under <b>Create record (POST) request schema</b> use the drop down list and select <b>Custom schema</b>.<br><br>
![](images/57.png)

20. Click on <b>ADD PROPERTY</b>. Rename the <b>Key</b> in <b>PROPERTIES</b> to “<i>base64</i>”.<br><br>
![](images/58.png)

21.  Add another property and rename it to “<i>fileName</i>” and click on <b>SAVE DATA ENTITY</b>. <br><br>
![](images/59.png)

22. Click on <b>SAVE</b> on the top right corner of the screen.<br><br>
![](images/60.png)


## Create Logic for Upload button <a name="appnotification"></a>

1. Go to the **UI CANVAS**. Select the <b>Upload your Invoice</b> button and click on the grey bar on the bottom to open the logic composer. <br><br>
![](images/28.png)

2. By default, the trigger event will be <b>Component tap</b>.<br>
Now you will download a new component from the <b>MARKETPLACE</b>.

    > MARKETPLACE</b> contains hundreds of pre-built visual and logic components, which can be installed and used with minimum or no customization.
  Find more information on <a href="https://docs.appgyver.com/docs/marketplace?highlight=Market%20place">MARKETPLACE here</a>.

    ![](images/29.png)

3. Click on the <b>MARKETPLACE</b> search bar. You may search for “<i>pick image</i>”. Select the <b>Pick image from library </b>component.<br><br>
![](images/30.png)

4. Click on <b>INSTALL</b> to install the logic component in the library.<br><br>
![](images/31.png)

5. Drag and drop the <b>Pick image from library</b> under the <b>INSTALLED</b> tab into the logic canvas. Connect output node of the <b>Component tap</b> logic component with the <b>Pick image
from library</b> component. <br>

    > To do so, click on the node of the <b>Pick image from library</b> component. Now pull the node, creating a line that you can link to the node of the <b>Component tap</b> logic component.

    ![](images/32.png)

6. From the <b>CORE</b> tab of the component library drag and drop the <b>Set app variable</b> component into the canvas. In the same way, connect the node of the <b>Pick image from library</b> component to the <b>Set app variable</b> component.<br><br>
![](images/33.png)

7. In the <b>PROPERTIES</b> tab of the <b>Set app variable</b>, select the variable <b>Invoicescan</b>.<br><br>
![](images/34.png)

8. Open the binding menu for <b>Assigned value</b>. <br><br>
![](images/101.png)

9. Select <b>Output value of another node</b>.<br><br>
![](images/102.png)

10. You can see the available nodes in the canvas. Select <b>Pick image from library</b> node. A list of outputs from node will appear. Select <b>
path</b>.<br><br>
![](images/103.png)

11. Click on <b>SAVE</b>.<br><br>
![](images/104.png)

## Create Logic for Submit button <a name="rejnotification"></a>

1. Select the <b>Submit</b> button and click on the grey bar on the bottom to open the logic composer.<br><br>
![](images/63.png)

2. You will download a new component from the <b>MARKETPLACE</b>.<br><br>
![](images/64.png)

3. In the search bar, search for “<i>base64</i>” and select <b>Convert file to base64</b>
and install it. <br><br>
![](images/65.png)

4. Drag and drop <b>Convert file to base64</b> into the logic canvas.<br><br>
![Submit](images/66.png)

5. Connect the nodes of <b>Component tap</b> and <b>Convert file to base64</b>.
Open the binding menu for <b>Source file URL</b> of the <b>Convert file to base64</b> logic component.<br><br>
![Submit](images/67.png)

6. In the binding menu select <b>Data and Variables</b> and select <b>App variable</b>.<br><br>
![Submit](images/68.png)

7. Select <b>Invoicescan</b> and click on <b>SAVE</b>.<br><br>
![Submit](images/70.png)

8. From the <b>CORE</b> tab, drag and drop <b>Set app variable </b> component from the component library and connect the node with <b>Convert file to base64</b>.
<br>In the <b>PROPERTIES</b> tab, make sure the variable is <b>filename</b>, and now open the binding menu for the <b>Assigned value.</b><br><br>
![Submit](images/72.png)

9. Select <b>Formula</b> in the binding menu.<br><br>
![Submit](images/73.png)

10. Open the formula editor. Select <b>App variables</b> and double click on <b>appVars.name</b> to use the function.<br><br>
![Submit](images/74.png)

11. Add the following values.
<br><pre>+TIMESTAMP()+".png"</pre>
The overall formula will look like the following: <br>
<br><pre>appVars.name+TIMESTAMP()+".png"</pre>
Click on <b>SAVE</b>.<br><br>
![Submit](images/75.png)

12. Drag and drop <b>Create record</b> logic component into the logic canvas and connect the nodes with <b>Set app variable</b> component. In the <b>PROPERTIES</b> tab of the logic component check if the <b>Resource name</b> is <b>Documentupload</b>. Open the binding menu of <b>Record properties</b>.<br><br>
![Submit](images/76.png)

13. In the binding menu, select <b>Object with properties</b>.<br><br>
![Submit](images/77.png)

14.  Open the binding menu for <b>base64</b>.<br><br>
![Submit](images/78.png)

15. In the binding menu select <b>Formula</b> and open the formula editor. In the formula editor, enter the following formula:
<br><pre>REPLACE_ALL(outputs["Convert file to base64"].base64,"data:image/png;base64,","")</pre>
Click on <b>SAVE</b> button.<br><br>
![Submit](images/79.png)

16. Open the binding menu for <b>fileName</b>.<br><br>
![Submit](images/80.png)

17. In the binding menu, select <b>Data and Variables</b> and select <b>App variable</b>. Select the variable <b>filename</b> and click on <b>SAVE</b>.<br><br>
![Submit](images/81.png)

18. Save the bindings.<br><br>
![Submit](images/82.png)

19. Drag and drop another <b>Create record</b> logic component into the logic canvas and connect the nodes with <b>Create record</b> component.
Change the <b>Resource name</b> to <b>SendtoSPA</b>.						
Open the binding menu for <b>Record</b> properties.<br><br>
![Submit](images/83.png)

20. In the binding menu, select <b>Object with properties</b>.<br><br>
![Submit](images/84.png)

21. Open the binding menu for <b>filename</b>.<Br><br>
![Submit](images/85.png)

22. In the binding menu, select <b>Data and Variables</b>, then choose <b>App variable</b> and finally the variable <b>filename</b>.<br>
Click on <b>SAVE</b>.<br><br>
![Submit](images/86.png)

23. The folder name will be static, enter the value “<i>Invoices</i>”. <br><br>
![Submit](images/87.png)

24. Open the binding menu for the <b>employeename</b>.<br><br>
![Submit](images/88.png)

25. In the binding menu, select <b>Data and Variables</b>. Select <b>App variables</b> and then choose <b>name</b>.<br><br>
![Submit](images/89.png)

26. The <b>employeemail</b> will be static, enter the email provided to you "ad160-XXX@education.cloud.sap".  For example: "<i>ad160-087@education.cloud.sap</i>"<br><br>
![Submit](images/90.png)

27. Save the bindings.<br><br>
![Submit](images/91.png)

28. Drag and drop a <b>Toast</b> component.

    > This component displays a message.<br>

    Connect the nodes of the <b>Create record</b> component to the <b>Toast</b> component. Under the properties of the <b>Toast</b> component, enter "<i>Your Invoice has been submitted</i>" as the <b>Toast message</b>.<br><br>
    ![Submit](images/92.png)

29. **Save** your work.

## Summary <a name="processcondi"></a>

You have build an app and completed the below steps.

![Summary](images/Scenario_summary.png)

Continue to - [Exercise 2 - Install and configure Desktop Agent 3](../2_InstallDesktopAgent3/Readme.md) and get started with SAP Build Process Automation.
>>>>>>> Stashed changes
=======
# In this exercise, you will build your app in SAP Build Apps to upload invoice.

## Table of Contents

- [Create a new app project ](#project)
- [Create the sales order page](#process)
- [Enable SAP BTP authentication](#data)
- [Create data resource to SAP Build Process Automation](#aprrovalform)
- [Test the trigger](#appnotification)
- [Create data variable](#rejnotification)
- [Bind data variable to UI elements](#processcondition)
- [Add logic to trigger workflow](#autoapproval)
- [Run app](#save)

# Overview <a name="project"></a>

In this exercise, you will build your app in SAP Build Apps to upload invoices.

![Image](images/1000.png)

## Create a new app project <a name="project"></a>

1. From [SAP Build Lobby](https://da160-96ork4sc-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby), Go to the SAP Build lobby, and click on <b>Create</b>.<br>

<br>

![Image](images/100.png)

2. Select <b>Build an Application.</b>
   <br><br>
   ![Image](images/200.png)

3. Select <b>Web & Mobile Application.</b>
   <br><br>  
   ![Image](images/300.png)

4. For the project name, enter <i>Sales Order Trigger</i> then click <b> Create.</b>
   <br><br>
   ![Image](images/400.png)

## Create the sales order page <a name="process"></a>

1. By default your new application contains a page with title and text fields. In this step, you will focus on turning this page into your app, including how to build a UI and stylize the UI elements. <br><br>

2. Select the text field, and click the <b> X </b> to delete it. <br><br>![Title component](images/500.png)

3. Click on an open area, and in the <b>Properties</b> tab, change the <b>Page Name</b> to <i>Create Sales Order.</i><br><br> ![Image](images/600.png)

4. Select the <b> Style </b> tab. <br><br>![input component](images/700.png)

5. Click the <b> Background Color </b> (App Background), and then select New Palette.<br><br>![input properties]![Image](images/800.png)

6. For the color, enter _#F3D6A0_, name the color _SAP Orange Light_, and click <b> Save.</b>

7. Click the title field, and in the <b>Properties</b> tab change the <b>Content </b> text to _Sales Order Workflow_.<br><br>
   ![Image](images/900.png)

8. To the canvas, drag a Container component. With the container selected, in the <b> Properties </b> tab under Advanced Properties, change the <b> Component display name </b> to _Form_.

   ![Image](images/1100.png) <br>
   Still with the container selected, open the <b> Style </b> tab, and click <b> Edit </b> for the Layout Container. <br> ![Image](images/1200.png)
   For the background color, select **Level 4 background.** <br>
   For padding, set the padding on all 4 sides to 16px by going to **Theme** and selecting the **L** size. <br> ![Image](images/1300.png) <br>
   For **Effects**, create a shadow by setting these properties: <br>
   **Enable Shadow** : True <br>
   **Shadow**: Content Shadow 0 <br>
   **Color** : Any static color you like (I chose #8e8989) <br>
   Let’s save the style by scrolling up, clicking <b>New Style,</b> entering Layout _Form Container_, and clicking <b> OK.</b>

9. Inside the outer container, add another container, and inside that container add a text and input field. The result should look like this: <br><br>
   ![Image](images/1400.png) <br><br>
   For the inner container, go to **Layout** tab, and under **Layout** set the container to **Horizontal**. Then, set **Align components** to middle. <br>
   ![Image](images/1500.png) <br>
   For the text field, go to **Layout** tab and set the width to exactly 75px.<br>
   ![Image](images/1600.png)<br>
   For the input field, delete _Label_ from the **Label** property. <br><br>

10. From the Tree view, copy the inside container and paste it inside the outer ( Form ) container until you have 4 fields..<br>
    ![Image](images/1700.png)<br>
    <b>Fields </b> <br>
    Ship To Party <br>
    Material <br>
    Order Amount <br>
    Delivery Date<br>
    ![Image](images/1800.png)

11. At the bottom of the page (outside the outside container), add a button. In the **Properties** tab, set the **Label** to _Get Approval_. <br><br>
    ![Image](images/1900.png)

## Enable SAP BTP authentication <a name="data"></a>

You need to enable SAP BTP authentication since you want to use SAP BTP destinations.

1.  Go to the <b>Auth</b> tab.<br>

2.  Click Enable <b>Authentication</b>.<br>
    ![Image](images/2000.png)

3.  Select <b> SAP BTP Authentication.</b> On the confirmation popup, click <b>OK</b>.<br>

## Create data resource to SAP Build Process Automation <a name="approvalform"></a>

As part of setting up SAP Build Process Automation, you created a destination so you can make calls to the SAP Build Process Automation APIs, including the one that lets you trigger a workflow.
<br><br>
Now you will set up the connection from your app to SAP Build Process Automation on your tenant, using that destination. <br><br>
<br>

1.  Open the **Data** tab, at the top of the page <br><br>
2.  Scroll down, and click <b>Create Data Entity > SAP BTP Destination REST API Integration</b>.<br>
    The configuration screen appears, starting with the **Base** panel. <br>
    ![Image](images/2100.png)

3.  On the Base panel, enter the following:<br><br>
<table>
  <tr>
    <th>Field</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Data resource name</td>
    <td><i>Trigger Workflow</i></td>
  </tr>
  <tr>
    <td>BTP destination name</td>
    <td><i>sap-process-destination (or the destination you created, if you created your own)</i> </td>
  </tr>
  </table> <br>

![Image](images/2200.png)

<br><br>
Under <b>Resource schema</b>, click Add New and add a field of type <i>Object</i> and with the name **salesorderdetails** .<br><br>
Click on the new field, and add the following sub-fields to the object: <br>

![Image](images/2300.png)
<br>
<b>IMPORTANT:</b> Click on the <b> Add New </b> button BELOW the salesorderdetails field. <br><br>

<table>
  <tr>
    <th>Field Name</th>
    <th>Type</th>
  </tr>
  <tr>
    <td>ShipToPartyl</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Material</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>OrderAmount</td>
    <td>Number</td>
  </tr>
  <tr>
    <td>ExpectedDeliveryDate</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Division</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>SalesOrderType</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>ShippingCountry</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>SalesOrganisation</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>DistributionChannel</td>
    <td>Text</td>
  </tr>

</table>

4.  Click the **create** panel.<br>
    Then enable the create action with the toggle button.<br><br>
    ![Image](images/2400.png) <br>
    ![Image](images/2500.png) <br>

5.  For **Request headers**, click the binding **X**, then **List of values**.<br>

Click **Add a value**, and add the following key-value pair:<br>

<table>
  <tr>
    <th>Field Name</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Header name</td>
    <td>Content-Type</td>
  </tr>
  <tr>
    <td>Header value</td>
    <td>application/json</td>
  </tr>
  </table>
        ![](images/32.png)
        Click <b>Save.</b>

6.  For <b>Request body mapper,</b> click the binding <b> X</b>, then <b>Formula > Create formula.</b><br>
    Enter the following for the formula – replace <your definition ID> with the ID for your process:<br><br>
    " ENCODE_JSON({ "definitionId": "<your definition ID>", "context": query.record })" <br><br>
    Click <b>Save </b>twice.

        ![](images/33.png)

7.  Click **Save Data Resource** (bottom right). <br>
    Click Save (in the upper right to save all your changes to the project).<br>
    ![](images/34.png)

## Test the trigger <a name="appnotification"></a>

1. Open the data resource again by clicking it.<br>
   ![Images](images/2600.png)

2. Click **create** on the left, and then the **Test tab**..<br>

3. Enter values for the fields (really, you only need to enter an order amount), and then scroll down and click **Run Test**. <br>
   ![Images](images/2700.png)

**IMPORTANT**: Date fields must be in the format of 2022-12-25 and the order amount must be a number.<br><br>
If all works **OK**, you will get a **201** status code and a response with information about the process instance you just triggered, something like this: <br><br>
Javascript: <br><br>
{
"id": "54988e48-8056-11ed-9a13-eeee0a99244a", <br>
"definitionId": "us10.my-account.salesorderapprovals.orderProcessing", <br>
"definitionVersion": "6",<br>
"subject": "Order Processing",<br>
"status": "RUNNING",<br>
"businessKey": "54988e48-8056-11ed-9a13-eeee0a99244a",<br>
"parentInstanceId": null,<br>
"rootInstanceId": "11118e48-8056-11ed-9a13-eeee0a99244a", <br>
"applicationScope": "own",<br>
"projectId": "us10.my-account.salesorderapprovals",<br>
"projectVersion": "1.0.5",<br>
"startedAt": "2022-12-20T11:06:19.318Z", <br>
"startedBy": "sb-clone-41c25609-33a1-9999-97d8-34fcd2316008!b3591|workflow!b116",<br>
"completedAt": null<br>
}<br>
![Images](images/2800.png) <br>

If you’ve gotten to here, your integration with SAP Build Process Automation is working!!<br>
You can go into the SAP Build Process Automation monitoring and see there the process you just triggered, and check the context to make sure the parameters were sent properly. <br>
![Images](images/2900.png)<br>
You can also check the Inbox to see the forms were created and the values properly passed into the workflow.<br>
![Images](images/3000.png)<br>

## Create data variable <a name="rejnotification"></a>

1. Back on the UI canvas, select **Variables**.<br>

2. On the left, click **Data Variables**.<br>

3. Click **Add Data Variable**, and choose **Trigger Workflow** as the data resource on which to base the data variable. <br>
   ![Image](images/3001.png)

4. On the right, choose **New data record**.<br>
   ![Image](images/3002.png)

5. Click **Save** (upper right).<br>

## Bind data variable to UI elements <a name="processcondition"></a>

1. Go back to **View** so you can see the UI canvas.<br>

2. Click on the first input field (for **Customer**).
   In the Properties tab, click the **X** next to the **Value** field, and select **Data and Variables > Data Variables > Trigger Workflow1 > shipToParty**.<br>
   ![Image](images/3003.png)

3. Click **Save**<br><br>

4. Click on the second input field (for **Material**). <br>
   In the Properties tab, click the **X** next to the Value field, and select **Data and Variables > Data Variables > Trigger Workflow1 > material.** <br>
   Click **Save**<br><br>

5. Click on the third input field (for **Amount**). <br>
   In the Properties tab, click the **X** next to the Value field, and select D**ata and Variables > Data Variables > Trigger Workflow1 > orderAmount.** <br>
   Click **Save**<br><br>

6. Click on the fourth input field (for **Delivery Date**).
   In the **Properties** tab, click the **X** next to the Value field, and select **Data and Variables > Data Variables > Trigger Workflow1 > expectedDeliveryDate.**
   Click **Save**<br><br>

7. Click **Save** (upper right).

## Add logic to trigger workflow <a name="autoapproval"></a>

1. Click on the **Get Approval** button, and open the logic canvas by clicking **Add logic to Button1** at the bottom right.<br>
   ![Image](images/3004.png)<br>

2. Drag a **Create record** flow function onto the canvas, and connect the component tap event to it.<br> ![Image](images/3005.png)<br>

3. Click on the **Create record** flow function and configure it in the **Properties** pane on the right.
   <br>
   For **Resource name**, this should already be set to **Trigger Workflow**, since you have only one data resource.<br> ![Image](images/3006.png) <br>
   For **Record** , you have to bind each of the data variable fields to the appropriate record field. <br>
   There are many ways to do binding. For **Properties** , you will use a formula. Click on the object binding button: <br> ![Image](images/3008.png) <br>
   Click **Formula** , then click on the existing formula, and replace it with the following: <br>
   Javascript: <br>
   {salesorderdetails: {division: "1010", orderAmount: NUMBER(data["Trigger Workflow1"].salesorderdetails.orderAmount), shipToParty: data["Trigger Workflow1"].salesorderdetails.shipToParty, salesOrderType: "OR", shippingCountry: "Barbados", salesOrganisation: "10", distributionChannel: "1000", expectedDeliveryDate: data["Trigger Workflow1"].salesorderdetails.expectedDeliveryDate, material: data["Trigger Workflow1"].salesorderdetails.material}}
   <br>

4. Click **Save**.<br>

5. Drag a **Toast** flow function onto the canvas, and connect the **top** output of the Create record flow function to it. <br> ![Image](images/3007.png)<br>

6. Click on the **Toast** flow function and configure it in the **Properties** pane on the right. <br>
   For **Toast message**, click on the **ABC**, and then select **Formula > Formula**. <br>
   Erase the quotation marks, and enter the following formula: <br>
   "Triggered process with ID: " + outputs["Create record"].response.id <br>
   Click **Save**.
   <br><br>

7. Click **Save** (upper right).

## Run App <a name="save"></a>

1. Click the **Launch** tab, and then **Open Preview Portal**. <br>
   ![Image](images/3009.png) <br>
2. Click **Open web preview** (left). <br>

3. Select your project, **Select Order Trigger**.<br> ![Image](images/3010.png) <br>
4. Enter the following values in your form: <br>
<table>
  <tr>
    <th>Field Name</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Customer</td>
    <td>Joe's Bikes</td>
  </tr>
  <tr>
    <td>Material</td>
    <td>HT-1000</td>
  </tr>
  <tr>
    <td>Amount</td>
    <td>1000</td>
  </tr>
  <tr>
    <td>Delivery Date</td>
    <td>2023-03-31</td>
  </tr>
  </table> <br>
5. Click Get Approval. <br>
   You process should be triggered and require approval (since the amount is 1000 or above). <br>
   You should see the toast message indicating the workflow was triggered, and with the process instance ID. <br>

   ![Image](images/3011.png)
   You can also see the results of the call in SAP Build Process Automation. <br>
   Go to the Monitor tab, then Process and Workflow Instances. The first one should be the one you just triggered.<br>
   You can see the new process instance.<br>
   You can see the context, which is the values sent with the API. <br>
   You can also see the execution log, which in this case ran the auto-approve task because the amount was below 100000.<br>
   The context field in yellow are the ones that you entered via the UI.<br> ![Image](images/3012.png)
   You can also see that the process instance ID is the same: in the toast message and in the upper right of the Monitor tab.
>>>>>>> Stashed changes
