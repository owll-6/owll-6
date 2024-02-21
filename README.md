import time

t = time.localtime(time.time())
localtime = time.asctime(t)
str ="Current Time:" + time.asctime(t)
print ("________________________________________________________________________________________________________________________________________________")
print(str)
import pyfiglet
ascii_banner = pyfiglet.figlet_format("          wifi band_2")
print(ascii_banner)

print ("________________________________________________________________________________________________________________________________________________")




import socket
import sys
# Create a TCP/IP socket 
stream_socket = ("socket.AF_INET. socket.SOCK_STREAM")

# Define host 
host = 'localhost'
# define the communication port 
port = input(     "___wsf Port      >>")
# Connect the socket to the port where the server is listening 
server_address = ((host, port))
print ("connecting")
stream_socket= ("server_address")
# Send data 
message = 'message'
stream_socket= ("message")
# response 
data = stream_socket


import socket
import sys
# Create a TCP/IP socket 
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# Define host 
host= ('localhost')
localhost= input("___enter IP host >>")
# define the communication port 
port = 8080
# Bind the socket to the port 
sock.bind((host, port))
# Listen for incoming connections 
sock.listen(1)
# Wait for a connection 
print ('waiting for a connection')
connection, client = sock.accept()
print ("connected")
# Receive the data in small chunks and retransmit it 
data = connection.recv(16)
print ('received "%s"') % data
if data:
    connection.sendall(data)
else:
    print ("no data from', client")
# Close the connection 
connection.close()


import dnspython as dns
import dns.resolver
result = dns.resolver.query('mail.google.com', 'CNAME')
for cnameval in result:
 print ("cname target address:', cnameval.target")
 result = dns.resolver.query('mail.google.com', 'MX')
for exdata in result:
    print ('MX Record:, exdata.exchange.text()')



import time
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
("http://localhost")

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure HTTP basic authorization: Basic.


# Enter a context with an instance of the API client
 # Create an instance of the API class
   
account_id = '9900000' # str | Your Bandwidth Account ID
create_call = bandwidth.CreateCall() 
 # CreateCall | JSON object containing information to create an outbound call

try:
     # Create Call api_response = api_instance.create_call("account_id, create_call"")
     print ("The response of CallsApi->create_call:\n")
     pprint ("api_response")
except ApiException as e:
   print ("Exception when calling CallsApi->create_call: %s\n" % e)
import time
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
("http://localhost")

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure HTTP basic authorization: Basic.


# Enter a context with an instance of the API client
 # Create an instance of the API class
   
account_id = '9900000' # str | Your Bandwidth Account ID
create_call = bandwidth.CreateCall() 
 # CreateCall | JSON object containing information to create an outbound call

try:
        # Create Call
        api_response = api_instance.create_call(account_id, create_call)
        print("The response of CallsApi->create_call:\n")
        pprint(api_response)
except ApiException as e:
        print("Exception when calling CallsApi->create_call: %s\n" % e)

import time
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
("http://localhost")

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure HTTP basic authorization: Basic.


# Enter a context with an instance of the API client
 # Create an instance of the API class
   
account_id = '9900000' # str | Your Bandwidth Account ID
create_call = bandwidth.CreateCall() 
 # CreateCall | JSON object containing information to create an outbound call

try:
        # Create Call
        api_response = api_instance.create_call(account_id, create_call)
        print("The response of CallsApi->create_call:\n")
        pprint(api_response)
except ApiException as e:
        print("Exception when calling CallsApi->create_call: %s\n" % e)
        
import psutil
import time

UPDATE_DELAY = 1 # in seconds

def get_size(bytes):
    """
    Returns size of bytes in a nice format
    """
    for unit in ['', 'K', 'M', 'G', 'T', 'P']:
        if bytes < 1024:
            return f"{bytes:.2f}{unit}B"
        bytes /= 1024
        
 # get the network I/O stats from psutil
io = psutil.net_io_counters()
# extract the total bytes sent and received
bytes_sent, bytes_recv = io.bytes_sent, io.bytes_recv

while True:
    # sleep for `UPDATE_DELAY` seconds
    time.sleep(UPDATE_DELAY)
    # get the stats again
    io_2 = psutil.net_io_counters()
    # new - old stats gets us the speed
    us, ds = io_2.bytes_sent - bytes_sent, io_2.bytes_recv - bytes_recv
    # print the total download/upload along with current speeds
    print(f"Upload: {get_size(io_2.bytes_sent)}   "
          f", Download: {get_size(io_2.bytes_recv)}   "
          f", Upload Speed: {get_size(us / UPDATE_DELAY)}/s   "
          f", Download Speed: {get_size(ds / UPDATE_DELAY)}/s      ", end="\r")
    # update the bytes_sent and bytes_recv for next iteration
    bytes_sent, bytes_recv = io_2.bytes_sent, io_2.bytes_recv             


import psutil
import time
import os
import pandas as pd

UPDATE_DELAY = 1 # in seconds

def get_size(bytes):
    """
    Returns size of bytes in a nice format
    """
    for unit in ['', 'K', 'M', 'G', 'T', 'P']:
        if bytes < 1024:
            return f"{bytes:.2f}{unit}B"
        bytes /= 1024
       
 # get the network I/O stats from psutil on each network interface
# by setting `pernic` to `True`
io = psutil.net_io_counters(pernic=True)

while True:
    # sleep for `UPDATE_DELAY` seconds
    time.sleep(UPDATE_DELAY)
    # get the network I/O stats again per interface 
    io_2 = psutil.net_io_counters(pernic=True)
    # initialize the data to gather (a list of dicts)
    data = []
    for iface, iface_io in io.items():
        # new - old stats gets us the speed
        upload_speed, download_speed = io_2[iface].bytes_sent - iface_io.bytes_sent, io_2[iface].bytes_recv - iface_io.bytes_recv
        data.append({
            "iface": iface, "Download": get_size(io_2[iface].bytes_recv),
            "Upload": get_size(io_2[iface].bytes_sent),
            "Upload Speed": f"{get_size(upload_speed / UPDATE_DELAY)}/s",
            "Download Speed": f"{get_size(download_speed / UPDATE_DELAY)}/s",
        })
    # update the I/O stats for the next iteration
    io = io_2
    # construct a Pandas DataFrame to print stats in a cool tabular style
    df = pd.DataFrame(data)
    # sort values per column, feel free to change the column
    df.sort_values("Download", inplace=True, ascending=False)
    # clear the screen based on your OS
    os.system("cls") if "nt" in os.name else os.system("clear")
    # print the stats
    print(df.to_string())
    
    
