twilio roundtrip demo

This demo exposes the twilio API as a REST service.

It also polls twilio for new messages and responds to them.


What you need to run this demo:
	1. A twilio account
		- you'll get a twilio phone number
	2. have authorized your phone on twilio.
  		- only authorized phones can receive messages from trial accounts


How to run the demo:
	- change the credentials in src/main/resources/mule-app.dev.properties.  You need:
		twilio.phoneNumber=
		twilio.accountSid=
		twilio.authToken=
	- open src/main/app/mule-app.properties
		- ensure mule.env=dev
		- or make a copy of src/main/resources/mule-app.dev.properties and
		  rename to src/main/resources/mule-app.personal.properties
	- run or debug the project
	- use the APIkit Console to send a text.
		- click on GET
		- click on "Try It"
		- enter your mobile phone number
		- enter your message
		- click on GET
	- you'll see a reply message on your phone.