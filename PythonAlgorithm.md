# Scenario
You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.
# Project Description
In this project, I am going to write a Python algorithm that allows me to remove a list of restricted IP addresses from a given list of currently allowed IP addresses. I am going to open a file, read it, perform some parsing so that I can work with the data, then write the result into the initial file (removing all previous contents). This algorithm will allow me to quickly and effectively remove people's access in areas that they don't need to be to perform their jobs.
# File contents
The file I will be working with (named `"allow_list"` contains the following contents:
```
ip_address
192.168.25.60
192.168.205.12
192.168.97.225
192.168.6.9
192.168.52.90
192.168.158.170
192.168.90.124
192.168.186.176
192.168.133.188
192.168.203.198
192.168.201.40
192.168.218.219
192.168.52.37
192.168.156.224
192.168.60.153
192.168.58.57
192.168.69.116
```
# Open the file that contains the allow list
I will first assign a string containing this file name to the `import_file` variable. Then, I will assign a list of IP addresses to be removed to the variable `remove_list`. The file that I want to open is called `"allow_list.txt"`. To do this, I will be using the `with` statement along with an `open()` function, with *read* (`"r"`) as the action I want to perform on this file.
```
# Assign `import_file` to the name of the file 

import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# First line of `with` statement

with open(import_file, "r") as file:
```
# Read the file contents
Next, I will use the `.read()` method to convert the contents of the allow list file into a string so that I can read them. I will store this string in a variable called `ip_addresses`.
```
# Assign `import_file` to the name of the file 

import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Build `with` statement to read in the initial contents of the file

with open(import_file, "r") as file:

  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

  ip_addresses = file.read()`
```
# Convert the string into a list
In order to remove individual IP addresses from the allow list, the IP addresses need to be in a list format. Therefore, I must use the `.split()` method to convert the `ip_addresses` string into a list.
```
# Assign `import_file` to the name of the file 

import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Build `with` statement to read in the initial contents of the file

with open(import_file, "r") as file:

  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses` from a string to a list

ip_addresses = ip_addresses.split()
```
# Iterate through the remove list
A second list called `remove_list` contains all of the IP addresses that should be removed from the `ip_addresses` list. I'm going to set up the header of a `for` loop that will iterate through the `ip_addresses`, using `element` as the loop variable.
```
# Assign `import_file` to the name of the file 

import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Build `with` statement to read in the initial contents of the file

with open(import_file, "r") as file:

  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses` from a string to a list

ip_addresses = ip_addresses.split()

# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`

for element in ip_addresses:
```
Suppose I put the code `print(element)` inside the `for` loop. The contents printed should be the exact same as the file contents listed above.
# Remove IP addresses that are on the remove list
In the body of my `for` loop, I'm going to add code that will remove all the IP addresses from the allow list that are also on the remove list. To do this, first, I will create an `if` statement what determines if the current `element` is found in the `remove_list`. If so, I will apply the `.remove()` method to the `ip_addresses` list and remove the IP addresses identified in the loop variable `element`. 
```
# Assign `import_file` to the name of the file 

import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Build `with` statement to read in the initial contents of the file

with open(import_file, "r") as file:

  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses` from a string to a list

ip_addresses = ip_addresses.split()

# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`

for element in ip_addresses:
  
  # Build conditional statement
  # If current element is in `remove_list`,
  
    if element in remove_list:

        # then current element should be removed from `ip_addresses`

        ip_addresses.remove(element)
```
Assume I printed the `ip_addresses` variable right after this `for` loop, it will print the list with the removed IP addresses found in `remove_list`. However, we want to write the list into the file as strings, therefore, we must convert the list back into a string.
# Update the file with the revised list of IP addresses
Now that I have removed the few IP addresses from the `ip_addresses` variable, I can complete the algorithm by updating the file with this revised list. To do this, I must first convert the `ip_addresses` list back into a string using the `.join()` method (the `.join()` method concatenates the elements of an iterable into a string). I need to apply `.join()` to the string `"\n"` in order to separate the elements in the file by placing them on a new line. Then, I will use another `with` statement (as well as another `open()` method, but this time using the *write* (`"w"`) as the action) and the `.write()` method to write over the file assigned to the `import_file` variable.
```
# Assign `import_file` to the name of the file 

import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Build `with` statement to read in the initial contents of the file

with open(import_file, "r") as file:

  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

  ip_addresses = file.read()

# Use `.split()` to convert `ip_addresses` from a string to a list

ip_addresses = ip_addresses.split()

# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`

for element in ip_addresses:
  
  # Build conditional statement
  # If current element is in `remove_list`,
  
    if element in remove_list:

        # then current element should be removed from `ip_addresses`

        ip_addresses.remove(element)

# Convert `ip_addresses` back to a string so that it can be written into the text file 

ip_addresses = "\n".join(ip_addresses)    

# Build `with` statement to rewrite the original file

with open(import_file, "w") as file:

  # Rewrite the file, replacing its contents with `ip_addresses`

  file.write(ip_addresses)
```
# Final draft
To put this all together, I will put all of this inside a functioncalled `update_file`, thus, making it easier to use later on. This function takes in two parameters, the first being the name of the text file that contains IP addresses (call this parameter `import_file`). The second parameter is a list that contains IP addresses to be removed (call this parameter `remove_list`).
```
def update_file(import_file, remove_list):

    # Build `with` statement to read in the initial contents of the file

    with open(import_file, "r") as file:

        # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

        ip_addresses = file.read()

    # Use `.split()` to convert `ip_addresses` from a string to a list

    ip_addresses = ip_addresses.split()

    # Build iterative statement
    # Name loop variable `element`
    # Loop through `ip_addresses`

    for element in ip_addresses:

        # Build conditional statement
        # If current element is in `remove_list`,

        if element in remove_list:

            # then current element should be removed from `ip_addresses`

            ip_addresses.remove(element)

    # Convert `ip_addresses` back to a string so that it can be written into the text file 

    ip_addresses = "\n".join(ip_addresses)       

    # Build `with` statement to rewrite the original file

    with open(import_file, "w") as file:

        # Rewrite the file, replacing its contents with `ip_addresses`

        file.write(ip_addresses)
```
# Summary
And there we have it, an algorithm that uses a list of disallowed IP addresses to remove the IP addresses from the list of allowed IP addresses. The algorithm first opens up a file that contains a list of allowed IP addresses. The algorithm reads the contents, converts that into a list since it was initially a string (using the `.split()` method). Then, it loops through each element of that newly created list, comparing each element to see if it is found in the list of disallowed IP addresses. If it is found, it uses the `.remove()` method to remove the corresponding IP address. Once that's done, the algorithm then converts the list back into a string using the `.join()` method (using a new line as a separator), and then finally rewrites the original file with the new list with disallowed IP addresses removed.