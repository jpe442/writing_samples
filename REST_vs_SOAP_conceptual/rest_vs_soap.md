# Understanding the Rise of REST API

## Web Service API and REST

Web service APIs (Application Programming Interfaces) are pieces of software or systems that grant access to various services for building web applications. The services are available by sending requests and getting responses via HTTP protocol (or HTTPS for encrypted resources) similar to calling a webpage in a browser. For instance, one of the more popular web services today is Google Maps API. Of course, you can use a browser to visit http://maps.google.com and from there use the Google Maps service through the web browser to get various kinds of map-related information, e.g. directions from one place to another. However, a developer you might desire to include similar map functions in your application. 

However, maybe you are building a website for an airport and want users to be able to check up-to-date directions from where they are to the airport. Instead of building an entire map application, which would be far beyond the scope or budget of the website, your website can make a request to the Google Maps API and return directions from the user's location to the airport. This *webhook* makes the website more efficient for users, encourages better use of the website, and hopefully leads to more satisfied airport customers.

While various types of web service APIs are still in use, the primary type of API consumed for web development is REST API. REST (REpresentational State Transfer), as a model, has some specific characteristics outlined by the model's inventor Roy Fielding. However, since those specifications are not essential for request and response functionality they are not standards that must be followed precisely. This makes developing REST APIs quite flexible. Accordingly, "RESTful" is sometimes used as a more accurate name for the general architectural style. The primary shared features of RESTful APIs are::

* **Client/server independent**​: Clients or servers can be changed with no necessary ramifications to the APIs functionality. They are not integrally linked.
* **Stateless​**: The server does not store any session state data. The browser client stores any such data.
* **Cacheable**: ​Responses can be saved to the browser client's cache and called back up without resending a
request to the URL.

Websites also feature these properties, highlighting how REST terminology is the nomenclature of the web. When you enter a URL address into your browser's address bar, the browser sends a GET request to that URL, which returns the webpage information in HTTP protocol. This HTTP response is then interpreted by the browser and finally rendered as the graphical webpage your browser displays. REST APIs work quite similarly. REST APIs have resources accessed via URL addresses, called ‘endpoints’. Using the standard HTTP verbs, GET, POST, PUT, and DELETE, developers configure the endpoints with specific parameters to retrieve and manipulate desired information. An endpoint configuration can be as simple as a GET request in HTTP protocol. In this way, REST leverages existing HTTP protocol features for simple and flexible retrieval of information.

## Why REST?

The use of REST API has largely surpassed other types (SOAP, XML-RPC, JSON-RPC) in utilization, specifically in mobile app development. One way to further understand REST architecture and the rapid adoption of REST API is by comparison with the formerly dominant web service API: SOAP API.
 
Like all web service APIs, SOAP (Single Object Access Protocol) typically utilizes HTML protocol for sending and receiving information. However, SOAP requires a standardized XML envelope to describe that information in a specific manner in order for requests and responses to be parsed without error. 

If you do not implement the specific XML schema as specified, the response fails to achieve the desired request. This is because request/response specifications for a specific SOAP API are described in an accompanying WSDL (Web Services Description Language) file, which is necessary to parse the requests and responses, like a translation manual. Since the XML is rendered machine-readable via processing the WSDL file using XSLT, this translation is automated. One benefit of this automation is that errors in requests are handled explicitly, alerting the user how the request failed. However, all this automated description and translation requires extra processing on both the client and server side. In this way SOAP is computationally heavy and slows web applications, especially in mobile contexts where bandwidth is limited.

In comparison, REST APIs require no HTML protocol description from the user or translation required from the machines involved. Instead, separate documentation is provided for the developer to consult for structuring requests so that desired responses are received. This lack of automation puts pressure on the documentation of the API to ensure tractable use, but it also makes REST API much computationally lighter than SOAP API. There is no protocol description to process. So there is a tradeoff between automatic translation of protocol, including explicit error handling, on the one side, and processing speed/less storage requirements on the other. In the context of web applications, the tradeoff favors REST architecture due to inherent bandwidth concerns. In this way, the rise in popularity of web services, especially on mobile devices, has driven the adoption of REST over SOAP and other web service APIs.

Lastly, because REST APIs are not bound to deliver responses in any particular format, the way SOAP requires XML, developers have more flexibility in obtaining the most effective format for the particular application they are building. In particular, JSON (JavaScript Object Notation) responses are often the most desired response format as they are easily parsed by JavaScript. Since browser clients can use JavaScript already, these responses can be easily interpreted by the web browser client itself. The whole process is then even more streamlined and efficient.

## Further Reading

Learn REST: A RESTful Tutorial​, by Todd Friedrich
Learn API Doc​, by Tom Preston
Understanding SOAP and REST Basics And Differences​, by John Mueller