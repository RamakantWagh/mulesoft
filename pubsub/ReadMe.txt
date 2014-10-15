This project demonstrates how to implement pub/sub using MuleSoft.

You will need to have activemq running somewhere.
The connectivity settings for activemq are in src/main/resources/mule-app.personal.properties
The jms.topic name is in src/main/app/mule-app.properties

Once activemq is running you can launch the debugger or run the application.

When up and running Studio will activate the APIkit Console.

You can test the pub/sub by clicking on /employees PUT
Click Try It
Click "Prefill with example"
Click PUT

In the Console you should see the logger output.

There is a bug in the current APIkit Console that will throw an error if you change the employee_type to "Remote" and click PUT again.
So copy the URL (http://localhost:8083/pubSub/console) and paste it into a browser.
Now you can change the employee_type to "Remote" and PUT

A couple things to note:

Look at the "Set JMS Header Properties".
See how #[json:[0]/employee_type] is used to extract the employee_type from the JSON payload coming in from the browser.

Also click on the "Configuration XML" tab of the employee_api.xml and see how the message selector was implemented. 
Currently you have to specify this in the XML as it is NOT exposed in the GUI.

        <jms:inbound-endpoint topic="${jms.topic}" connector-ref="Active_MQ" doc:name="JMS" >
        	<jms:selector expression="employee_type = 'Office'"/>
       	</jms:inbound-endpoint>

