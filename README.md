# Creating a Python-Algorithm for file Updates

## Project description

In this project I have a workplace scenario, where we manage restricted content access through an IP address allow list. The specific IP addresses are listed in the "allow_list.txt" file. Additionally, there's a separate remove list that specifies the IP addresses no longer authorized for access. To streamline this process, I developed an algorithm to automatically update the "allow_list.txt" file and remove the obsolete IP addresses from accessing the content.

## Open the file that contains the allow list
To kick off the algorithm, I initiated by opening the "allow_list.txt" file. Initially, I designated the file name as a string and assigned it to the import_file variable.
Then, I used a with statement to open the file for the second part:

![image](https://github.com/Fariasm213/Python-Algorithm/assets/141985599/ca3a7e04-e2df-49a6-bc30-030d4c0dd700)

Incorporating the "with" statement in my algorithm, I utilized the .open() function in read mode to access the allow list file for reading purposes. The primary aim of opening the file was to retrieve the stored IP addresses within the allow list. Employing the "with" keyword aids in resource management by automatically closing the file upon exiting the "with" statement. Within the code block with open(import_file, "r") as file:, the open() function is configured with two parameters. The first specifies the file to be imported, and the second designates the intended action with the file. In this instance, "r" signifies the intention to read the file. The use of the "as" keyword assigns a variable named file to store the output of the .open() function while operating within the "with" statement.

## Read the file contents
In order to read the file contents, I used the .read() method to convert it into the string.

![image](https://github.com/Fariasm213/Python-Algorithm/assets/141985599/f48f4b94-8d72-48e9-8e63-d7f1ff3997c0)

When employing the .open() function with the "r" argument for "read," I utilized the .read() function within the "with" statement's body. The .read() method effectively transforms the file into a string, enabling me to comprehend its contents. I implemented the .read() method on the file variable specified in the "with" statement and assigned the resulting string output to the variable ip_addresses.
To recap, this piece of code reads the contents of the "allow_list.txt" file and converts them into a string format. This string serves as a valuable resource for organizing and extracting data within my Python program.

## Convert the string into a list
In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the .split() method to convert the ip_addresses string into a list:

![image](https://github.com/Fariasm213/Python-Algorithm/assets/141985599/ad97abd0-f90f-48e3-bfd7-f927f314e1c3)

The use of the .split() function involves appending it to a string variable. This function operates by transforming the contents of a string into a list. The objective of applying the .split() function to the ip_addresses variable is to facilitate the removal of IP addresses from the allow list. By default, the .split() function segments the text by whitespace, creating individual list elements.

In this algorithm, the .split() function processes the data contained in the ip_addresses variable, which is initially a string of IP addresses separated by whitespace. Consequently, this function converts the string into a list of distinct IP addresses. To preserve and utilize this list, I subsequently reassigned it to the ip_addresses variable.

## Iterate through the remove list
A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a for loop:

![image](https://github.com/Fariasm213/Python-Algorithm/assets/141985599/0eabdf77-eb68-4500-a04a-28c97f18d813)

In Python, the for loop is used to iterate over a specified sequence, executing code statements for each element. In the context of this Python algorithm, the overarching goal of the for loop is to implement specific code statements for all elements within a given sequence. The for loop commences with the "for" keyword, followed by the loop variable element and the "in" keyword. The "in" keyword signifies the iteration through the sequence ip_addresses, assigning each value to the loop variable element.

## Remove IP addresses that are on the remove list
In order to achieve the objective of my algorithm, which involves eliminating any IP address from the allow list (ip_addresses) that is also present in the remove_list, I utilized the following code. Since there were no duplicates in ip_addresses, the code effectively addresses this task:

![image](https://github.com/Fariasm213/Python-Algorithm/assets/141985599/e89c7912-b46b-4122-a454-d5797c0a2066)

First, within my for loop, I created a conditional that evaluated whether or not the loop variable element was found in the ip_addresses list. I did this because applying .remove() to elements that were not found in ip_addresses would result in an error. 

Then, within that conditional, I applied .remove() to ip_addresses. I passed in the loop variable element as the argument so that each IP address that was in the remove_list would be removed from ip_addresses.

## Update the file with the revised list of IP addresses 
As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the .join() method for this:

![image](https://github.com/Fariasm213/Python-Algorithm/assets/141985599/24141929-1387-4684-aea8-19acbd7862f3)

The .join() method consolidates all items within an iterable into a single string. This method is employed on a string that contains characters specifying how the elements in the iterable should be separated when joined into a string. In the context of this algorithm, I utilized the .join() method to transform the list ip_addresses into a string. This string, configured with the appropriate separation characters, was then passed as an argument to the .write() method when updating the "allow_list.txt" file.

Then, I used another with statement and the .write() method to update the file.

This time, I included a second argument, "w", in the open() function within my with statement. This argument signifies the intention to open a file for writing, allowing the overwriting of its existing contents. By using the "w" argument, I was able to invoke the .write() function within the body of the with statement. The .write() function is responsible for writing string data to a designated file, thereby replacing any pre-existing content.
In this scenario, my goal was to write the updated allow list as a string to the "allow_list.txt" file. This ensures that the restricted content becomes inaccessible to any IP addresses removed from the allow list. To accomplish this, I appended the .write() function to the file object (file) identified in the with statement. I provided the ip_addresses variable as the argument, specifying that the contents of the file specified in the with statement should be replaced with the data in this variable.


## Summary
In summary, I devised an algorithm to eliminate IP addresses listed in a remove_list variable from the "allow_list.txt" file, which contains approved IP addresses. The algorithm involved opening the file, converting its contents to a string for reading, and then transforming this string into a list stored in the ip_addresses variable. Subsequently, I iterated through the IP addresses in the remove_list, checking each element's presence in the ip_addresses list. If a match was found, I utilized the .remove() method to eliminate the element from ip_addresses. Following this, the .join() method was employed to revert ip_addresses back into a string, facilitating the overwriting of the "allow_list.txt" file with the updated list of IP addresses.

