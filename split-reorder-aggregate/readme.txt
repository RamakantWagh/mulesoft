splitter/resequencer/aggregator example

Run the Mule project.

You must now send the HTTP connector an HTTP request that includes a body with an attached XML file. 

Send a Post request to http://localhost:8081/ attaching XML to the body of the message. Sample XML is provided below.

The easiest way to do this is sending posts via a browser extension such as Postman (for Google Chrome), or the curl command-line utility.
<root xmlns:foo="http://www.foo.org/" xmlns:bar="http://www.bar.org">
    <actors>
        <actor id="1">Christian Bale</actor>
        <actor id="2">Liam Neeson</actor>
        <actor id="3">Will Ferrell</actor>
    </actors>
    <foo:singers>
        <foo:singer id="4">Dave Grohl</foo:singer>
        <foo:singer id="5">B.B. King</foo:singer>
        <foo:singer id="6">Weird Al</foo:singer>
    </foo:singers>
</root>

With the Resequencer in place, messages now reach the aggregator in the correct order and are assembled accordingly.