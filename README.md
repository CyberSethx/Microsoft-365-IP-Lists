   _____  .__                                 _____  __    ________   ________.________ 
  /     \ |__| ___________  ____  ___________/ ____\/  |_  \_____  \ /  _____/|   ____/ 
 /  \ /  \|  |/ ___\_  __ \/  _ \/  ___/  _ \   __\\   __\   _(__  </   __  \ |____  \  
/    Y    \  \  \___|  | \(  <_> )___ (  <_> )  |   |  |    /       \  |__\  \/       \ 
\____|__  /__|\___  >__|   \____/____  >____/|__|   |__|   /______  /\_____  /______  /  
._____________  .____    .__          __                                                
|   \______   \ |    |   |__| _______/  |_  ______                                      
|   ||     ___/ |    |   |  |/  ___/\   __\/  ___/                                      
|   ||    |     |    |___|  |\___ \  |  |  \___ \                                       
|___||____|     |_______ \__/____  > |__| /____  >                                                                                                         
           

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

Fortigate CLI import list :
config system external-resource
 edit "[Microsoft 365] Main IP list"
     set type address
     set resource "https://github.com/CyberSethx/Microsoft_IP_Lists/blob/main/Microsoft%20365%20IP%20address%20ranges.txt"
     set refresh-rate 15
 next
 edit "[Microsoft 365] additional IP list"
     set type address
     set resource "https://github.com/CyberSethx/Microsoft_IP_Lists/blob/main/Other%20endpoints%20not%20included%20in%20the%20Microsoft%20365%20IP%20Address.txt"
     set refresh-rate 15
 next


## Contributing

Contributions are welcome! If you have suggestions for improvements or encounter any issues, feel free to post here.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- [Microsoft 365 URLs and IP address ranges](https://learn.microsoft.com/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide)
- [Other endpoints not included in the Microsoft 365 IP Address](https://learn.microsoft.com/en-us/microsoft-365/enterprise/additional-office365-ip-addresses-and-urls?view=o365-worldwide)


