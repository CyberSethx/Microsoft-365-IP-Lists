<pre>
  __  __ _                           __ _     _____  __  ____  
 |  \/  (_) ___ _ __ ___  ___  ___  / _| |_  |___ / / /_| ___| 
 | |\/| | |/ __| '__/ _ \/ __|/ _ \| |_| __|   |_ \| '_ \___ \ 
 | |  | | | (__| | | (_) \__ \ (_) |  _| |_   ___) | (_) |__) |
 |_|  |_|_|\___|_|  \___/|___/\___/|_|  \__| |____/ \___/____/   
  ___ ____    _ _     _       
 |_ _|  _ \  | (_)___| |_ ___ 
  | || |_) | | | / __| __/ __|
  | ||  __/  | | \__ \ |_\__ \
 |___|_|     |_|_|___/\__|___/
</pre>                            
           
## Description

This project provides a comprehensive list of IPv4 addresses and subnets associated with Microsoft 365 services. It aims to assist network administrators in configuring firewalls, proxies, and other network devices to allow or monitor traffic to and from Microsoft 365.

Please note that the "[Microsoft 365] additional IP list" is required if you implement Hybrid Modern Auth and use Outlook Mobile App (Autodetect).

## Features

- Extracted all IPv4 addresses and subnets from official Microsoft 365 documentation.
- Provides the data in a plain text format, with one IP or subnet per line.
- Regularly updated to reflect changes in Microsoft's IP address allocations.

## Usage

- You can directly point to this public lists for example as an external list on your firewall (Below is an example with Fortigate CLI but this can work with a lot more)

## Example

<b>Fortigate CLI import list :</b>
<pre>
config system external-resource
 edit "[Microsoft 365] Main IP list"
     set type address
     set resource "https://raw.githubusercontent.com/CyberSethx/Microsoft_IP_Lists/refs/heads/main/%5BMicrosoft%20365%5D%20Main%20IP%20list"
     set refresh-rate 15
 next
 edit "[Microsoft 365] additional IP list"
     set type address
     set resource "https://raw.githubusercontent.com/CyberSethx/Microsoft_IP_Lists/refs/heads/main/%5BMicrosoft%20365%5D%20additional%20IP%20list"
     set refresh-rate 15
 next
</pre>
## Contributing

If you have suggestions for improvements or encounter any issues, feel free to post here.


## Referejces

- [Microsoft 365 URLs and IP address ranges](https://learn.microsoft.com/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide)
- [Other endpoints not included in the Microsoft 365 IP Address](https://learn.microsoft.com/en-us/microsoft-365/enterprise/additional-office365-ip-addresses-and-urls?view=o365-worldwide)


