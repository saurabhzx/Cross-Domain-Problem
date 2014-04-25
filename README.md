Cross-Domain-Problem
====================

I-Frame Cross Domain Policy Problem solution by postmessage 

Implementation of postmessage function of HTML

In computing, the same-origin-policy is an important concept in the web application security model.The policy permits scripts running on pages originating from the same site - a combination of scheme, hostname, and port number to access each other's DOM no specific restrictions, but prevents access to DOM on different sites.

Almost all web developers have at some point in their career faced cross-domain problems while building web apps. In a nutshell, you encounter these type of issues whenever an app wants to make client-side calls from a page hosted in one domain (for example, http://www.example.com/appPage.html) to a page or service hosted in a different domain (for example, http://www.iframe.com). By default, browsers block this type of communication for security reasons; they don't want malicious apps to grab data or execute code without users knowing it.

But the "postmessage" functun of HTML5 provide this remarkable solution for solving this.

In this tutorial we will take one parent.html and i-frame page and try to send message from Iframe.html to parent.html through parent.html.

First we will make parent.html which include


<html>
<head>
<script type="text/javascript">
window.addEventListener('message', receiveMessage, false);
function receiveMessage(event)
{

 alert("got message: "+event.data);

}
</script>
</head>
<title> Parent Page </title>
<body>
<iframe src="http://path/Iframe.html" width="500" height="500"></iframe>
</body>

</html>
 
This basically run the iframe and the window.addEventListener take care of the postmessage call from iframe.html.

Now make your Iframe.html page which include


<html>
<head>
<script>
function send(){
	window.parent.postMessage('Hello Parent Frame!', '*');
}
</script>
</head>
<title> IFrame Test </title>
<body>
<h1> Welcome </h1>
<p> Hello There </body>
<button onclick = "send()">Send</button>
</body>
</html>

 This basically call the window.parent.postMessage() function when the user click on to send function and send the message 'Hello Parent Frame!'.

Run the parent.html and click on the send button the parent page will receive the message 'Hello Parent Frame!' in alert box.

Hence the "postmessage" of HTML sove the problem of cross domain very easily and effectively.

