# Apigee Edge Resources Download
Use this tool to download configuration, information and entities from  Apigee Edge Organization.

  <b>Note :</b>
  The tool supports only bearer tokens when authenticating with your Apigee Edge Orgs.

# Data Download
With the tool, you can download below information and entities:

  <ul>
  <li>developers</li>
  
  <li>proxies (latest revision)</li>
  
  <li>shared flows</li>
  
  <li>products</li>
  
  <li>apps</li>
  
  <li>app keys</li>
  
  <li>KVMs (only env)</li>
  
  <li>Target Servers</li>
  
</ul>

# What data cannot be Downloaded

Please note that the following entities won't be downloaded as part of this tool.

<ul>
<li>Cache resources and cached values.</li>
<li>Environment resources such as virtualhosts, and keystores.</li>
<li>KVM entries for "encrypted" key-value maps. Encrypted values can't be retrieved using the management API. Get the values you're using in your old org, then add these values manually to the new org.</li>
</ul>


# Prerequisites

<ol>
  <li>Download and install Python at https://www.python.org/downloads.</li>
  <li>Configure Below Environment Variable for Python.</li>
  <li>C:\Users\Administrator\AppData\Local\Programs\Python\Python39\Scripts\</li>
  <li>C:\Users\Administrator\AppData\Local\Programs\Python\Python39\</li>
  <li>C:\Users\Administrator\AppData\Local\Programs\Python\Python39\Lib\site-packages</li>
</ol>

# Before you get started

Before you start downloading data, be sure to do the following to ensure that your org is in a stable state when downloading.
<ul>
<li>Freeze revisions on proxies in the Apigee Edge org you're downloading data from.</li>
<li>Pause the process of adding new proxies or features.</li>
</ul>

# Needed Configuration

There is no configuration for this tool except for the Python Configuration.

You will need Apigee Edge Org Name and a fresh Bearer Token .

<table>
  <tr>
    <td><b>Property</b></td>
    <td><b>Description</b></td>
  </tr>
  <tr>
      <td>Apigee Edge Org Name</td>
      <td>eg.  yesyter-eval</td>
  </tr>
  <tr>
      <td>Bearer Token</td>
      <td>eg.  eyJhbGciOiJSUzI1NiJ9.eyJqdGkiOiI0OTFlZjBhZi1kM2I5LTQ1MzUtODFkNi0zZTdkMDRiYTA0MmUiLCJzdWIiOiIyOTliNDA1Ni03NWM0LTQ3YzItYmE2My1mZDljNmI4NThlZTUiLCJzY29wZSI6WyJzY2ltLmVtYWlscy5yZWFkIiwic2NpbS5tZSIsIm9wZW5pZCIsInBhc3N3b3JkLndyaXRlIiwiYXBwcm92YWxzLm1lIiwic2NpbS5pZHMucmVhZCIsIm9hdXRoLmFwcHJvdmFscyJdLCJjbGllbnRfaWQiOiJlZGdlY2xpIiwiY2lkIjoiZWRnZWNsaSIsImF6cCI6ImVkZ2VjbGkiLCJncmFudF90eXBlIjoicGFzc3dvcmQiLCJ1c2VyX2lkIjoiMjk5YjQwNTYtNzVjNC00N2MyLWJhNjMtZmQ5YzZiODU4ZWU1Iiwib3JpZ2luIjoidXNlcmdyaWQiLCJ1c2VyX25hbWUiOiJuaXRpbm1haGF2aXIyMDIxQGdtYWlsLmNvbSIsImVtYWlsIjoibml0aW5tYWhhdmlyMjAyMUBnbWFpbC5jb20iLCJhdXRoX3RpbWUiOjE2NTE5MTIyMzQsImFsIjowLCJyZXZfc2lnIjoiZGQ5ZDFkN2YiLCJpYXQiOjE2NTE5MTIyMzQsImV4cCI6MTY1MTk1NTQzNCwiaXNzIjoiaHR0cHM6Ly9sb2dpbi5hcGlnZWUuY29tIiwiemlkIjoidWFhIiwiYXVkIjpbImVkZ2VjbGkiLCJzY2ltLmVtYWlscyIsInNjaW0iLCJvcGVuaWQiLCJwYXNzd29yZCIsImFwcHJvdmFscyIsInNjaW0uaWRzIiwib2F1dGgiXX0.kr_C4Jg3NGdme7KZGlkQGJGMQxapwinsuDqMb1HA1J_Epr2Gm_7UKrPpQslBJoGFFQ60SWB0wDjNcLXdOu7g-vjreRuGXYS76VDWPLML8ZAtp8moXjCNEd683AZHwcMCL4PqDStAaxfGlUYbPx27-RwBI-hP_7PwAFyefP8HNOxeq1hH6ZdZX-y0RcRXIsOabxU8_2-VR33kf0h2ZzCXCeqR-cxSx5omojTKf1YAKLyFt2l7rJtoXgMpwIJYwCZcU_qjax6WESEosAXHOpSPIjZlmFVh_4rRjoFGn8To4AUT8ImBe7jpvKQCNqwKkkWGkYZ6HnsPnFTBz6leVIKMhg</td>
  </tr>  
</table>



# How to Generate Bearer Token for Apigee Edge Org

Curl Command to Generate Apigee Egde Token

      curl -H "Content-Type:application/x-www-form-urlencoded;charset=utf-8" \       
      -H "Accept: application/json;charset=utf-8" \     
      -H "Authorization: Basic ZWRnZWNsaTplZGdlY2xpc2VjcmV0" \      
      -X POST https://login.apigee.com/oauth/token \      
      -d 'username=yourusername&password=yourpassword&grant_type=password'


# How to Use the tool

Method 1: 

<ul>
  <li>By Cloning the Repository Code </li>
  <li>
  To use the tool, open a command prompt and change to the root directory of the repository you cloned.
  </li>  
</ul>  

Method 2: 

<ul>
  <li>By Downloading the Repository as a zip file</li>
  <li>Extract the contents of the zip file.</li>  
  <li>Open a command prompt and change to the root directory to the extracted folder.</li>  
</ul>

Once we are at the root directory in the command prompt use below command to start downloading the resources
<ul>
  <li>python apigee_edge_tool.py</li>
</ul>

You will presented with several options to download information,resources and entities based on your use-case.
![image](https://user-images.githubusercontent.com/19343906/167250040-6bca84ed-4dfd-43d5-9724-68e8c3b2fcba.png)
There are 8 Available Options:
<ol>
  <li>Download All Resources</li>
  <li>Download Only Proxies </li>
  <li>Download Only SharedFlows </li>
  <li>Download Only Products</li>
  <li>Download Only Apps </li>
  <li>Download Only KVM </li>
  <li>Download Only Target Servers</li>
  <li>Download Only Developers</li>
</ol>

# Download Only Proxies
To download only Proxies from the Apigee Edge Org.
<ul>
  <li>Type <b>Proxy</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (391)](https://user-images.githubusercontent.com/19343906/166897336-e5f6251d-2c81-46b6-a369-10b734dc91d7.png)

# Download Only Shared Flows
To download only Shared Flows from the Apigee Edge Org.
<ul>
  <li>Type <b>SF</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (385)](https://user-images.githubusercontent.com/19343906/166896590-9a2bab2d-7713-4444-a5b7-e395aa63c332.png)

# Download Only Products
To download only Product from the Apigee Edge Org.
<ul>
  <li>Type <b>Product</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (386)](https://user-images.githubusercontent.com/19343906/166896742-7dff2a2b-7f6a-44b8-be41-e2e20d34acd7.png)

# Download Only Apps
To download only Apps from the Apigee Edge Org.
<ul>
  <li>Type <b>APP</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (387)](https://user-images.githubusercontent.com/19343906/166896851-9c2ff96b-c8e4-4ba0-abcd-22efc323cc62.png)

# Download Only KVMs
To download only KVMs from the Apigee Edge Org.
<ul>
  <li>Type <b>KVM</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (388)](https://user-images.githubusercontent.com/19343906/166896957-9cb5682e-ff30-43f7-a310-dfaa88d524d9.png)

# Download Only Target Servers
To download only Target Servers from the Apigee Edge Org.
<ul>
  <li>Type <b>TS</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (389)](https://user-images.githubusercontent.com/19343906/166897070-c67d1a42-942e-4f17-a240-65ce922bdf4b.png)

# Download Only Developers
To download only Developers from the Apigee Edge Org.
<ul>
  <li>Type <b>DEV</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (390)](https://user-images.githubusercontent.com/19343906/166897194-17323a97-1139-454e-a17a-956a821b7a69.png)

# Download All Resources
To download all Resources from the Apigee Edge Org.
<ul>
  <li>Type <b>ALL</b> ( Case Insensitive ) in the command prompt.</li>
</ul>

Below is the sample Screenshot.

![Screenshot (393)](https://user-images.githubusercontent.com/19343906/166897523-a24baafc-e1f2-480a-ba29-58f465366420.png)



The following folder structure with data will be created in your current directory.

![image](https://user-images.githubusercontent.com/19343906/167250492-f7e59b19-7232-4c8a-83c5-0d718852f1cc.png)

# Errors !!! 
Only 2 errors might occur while using the tool.

<b> 1. Invalid Credentials</b>

This error occurs if the user provided <b>Apigee Edge Org Name</b> or the <b>Bearer Token</b> is Invalid.

Below is the sample Screenshot.

![image](https://user-images.githubusercontent.com/19343906/167112664-527c1e4e-f696-4218-9f56-eb51042edf04.png)


<b> 2. Python is not recognized as an internal or external</b>

This error occurs if either python is not installed or the system environment variable for python is not set.

Below is the sample Screenshot.

![image](https://user-images.githubusercontent.com/19343906/167112266-2f1bf197-7542-428a-8dae-8f6b59fbf8af.png)





