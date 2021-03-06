# PubNub 3.4 Web Data Push Cloud-Hosted API - C# Mono 2.10.9 
##PubNub C Sharp (Mono for Linux) Usage

For a video walkthrough, check out https://vimeo.com/54805917 !

Open 3.4/PubNub-Messaging/PubNub-Console/PubNub-Messaging.csproj, the example Pubnub_Example.cs should demonstrate all functionality, asyncronously using delegates. The main functionality lies in the pubnub.cs file.

3.4/PubNub-Messaging/PubNubTest contains the Unit test cases.

Please ensure that in order to run on Mono the constant in the pubnub.cs file should be set to "true"
overrideTcpKeepAlive = true;

In the app.config both the projects the value of the key "initializeData" should be full path with rw access default value="/tmp/pubnub-messaging.log".

If you encounter an issue where SSL connections throw an exception, you need to import the root certificates using the command
mozroots --import --ask-remove

For more details please see:
http://www.mono-project.com/FAQ%3a_Security#Secure_Socket_Layer_.28SSL.29_.2F_Transport_Layer_Security_.28TLS.29

You can use either Newtonsoft.Json (recommended) or JsonFx as the serialization library. The example project has the references for both Newtonsoft.Json and JsonFx. You can retain either one.

To use JsonFx as the serialization library you need to use the pre-compiler directive USE_JSONFX and REMOVE the reference of Newtonsoft.Json from the project
Limitations of JsonFx: JsonFx doesn't support the serialization for type XmlDocument.

To use Newtonsoft.Json you need not specify any pre-compiler directive. This is the used as the default serialization library. You need to REMOVE the reference of JsonFx from the project and retain the reference of Newtonsoft.Json

System.Runtime.Serialization.Json/System.Web.Script.Serialization libraries are activated by using the pre-compiler directive USE_DOTNET_SERIALIZATION. The use of this library is NOT recommended for pubnub client created on mono platform as this causes issues in "talking" to pubnub clients developed for other platforms.

Dev environment setup:
- ubuntu 12.04
- Mono Develop 2.8.6.3+dfsg-2 or higher 
- Mono 2.10.8.1 or higher 

Report an issue, or email us at support if there are any additional questions or comments.


