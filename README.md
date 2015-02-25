Simple module test for saffire.

More info: http://saffire-lang.org


(make sure the Noxlogic directory is located in the ./modules directory)


Contents of: ./test.sf:
```
// imports the io class from the io module as "io" into the current namespace
import io;
// Import framework and http request
import Noxlogic::Framework;
import Noxlogic::Framework::Http::Request;

// Call the print method from our (imported) io class with a single argument
io.print("Hello world!\n");

// Create request object
request = Request();
request.setHttpMethod("get");
request.setUrl("http://saffire-lang.org");

// Request is automatically cast to string by the "print" method. (calls request.__string())
io.print(request, "\n");

// Run the framework
app = Framework();
response = app.run(request);

// Response is automatically cased: response.__string()
io.print("Response: ", response);
```
