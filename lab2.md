# Lab Report 2

## Part 1

Screenshot 1:

<img width="881" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/b93fca3d-650f-47d8-ad79-b8a1561b0cb8">

Screenshot 2:

<img width="1037" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/1e403d6b-0f23-420d-948b-682e07e49499">

Code:

<img width="761" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/173d899c-ada0-404a-8a97-cceaa69ba932">


For both of these screenshots, the only methods called are the main method and the handleRequest method within the `ChatServer` file.

The argument given to the main method is the port number, which is used to specify the port number where the server will be launched on, and both screenshots use port 3000.

The argument given to the `handleRequest` method is the url of the page that is accessed. The two screenshots differ in their url because they contain different queries for their differing messages.

With the first screenshot, the URI `url` changes from an empty url to the entire url of the request, which in this case is `http://localhost:3000/add-message?s=Hello=jpolitz`. 

Then, the string `chatHistory` changes from an empty string `""` to `jpolitz: Hello\n` because the new query from the url gets formatted and appended to the string after the first request to `/add-message`. 

Additionally, the `paramters` array changes from an empty string array to the value `{"s=Hello","user=jpolitz"}` because it splits the query across the `&` sign. 

The `message` string also changes from an empty string to `"Hello"` because it splits the first value within `parameters` across the `=` sign and takes the latter half. 

Lastly, the `user` string changes from an empty string to `"jpolitz"` because it splits the second value within `parameters` across the `=` sign and takes the latter half.

With the first screenshot, the URI `url` changes from an empty url to the entire url of the request, which in this case is `http://localhost:3000/add-message?s=How%20are%20you&user=yash`. 

Then, the string `chatHistory` updates again from `jpolitz: Hello\n` to `jpolitz: Hello\nyash: How are you` because the new query from the second url gets formatted and appended to the string after the second request to `/add-message`. 

Additionally, the `paramters` array changes from an empty string array to the value `{"s=How are you","user=yash"}` because it splits the query across the `&` sign. 

The `message` string also changes from an empty string to `"How are you"` because it splits the first value within `parameters` across the `=` sign and takes the latter half. 

Lastly, the `user` string changes from an empty string to `"yash"` because it splits the second value within `parameters` across the `=` sign and takes the latter half.

## Part 2

Absolute path to the private key: `/Users/jeremysu/.ssh/id_rsa`

<img width="1118" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/40e6dc83-586d-4d6b-932d-cc0fc7088736">

Absolute path to the public key: `~/.ssh/authorized_keys`

<img width="880" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/e1bd86e1-b497-42ca-b93e-d24e58d418dc">


Login without being prompted for password: 

<img width="566" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/41b1a35d-86b1-49b3-81ab-fa251db04e98">

## Part 3

Last week, I learned how to start a server on both my computer and remote hosts. I now have a basic understanding of how servers work and what commands are used to run them.
