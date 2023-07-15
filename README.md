<a name="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense">
    <img src="readme-images/DHCP_1.png" alt="Logo" width="100" height="100">
  </a>

  <h3 align="center">How to set up a DHCP Server with PFSense</h3>

  <p align="center">
    A Simple Network Project 
    <br />
    <a href="https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense">View Demo</a>
    ·
    <a href="https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/issues">Report Bug</a>
    ·
    <a href="https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li>
      <a href="#terminology">Terminology</a>
      <ul>
              <li><a href="#network">Network</a></li>
              <li><a href="#lan-and-subnet">Lan & Subnet</a></li>
              <li><a href="#dns">DNS</a></li>
              <li><a href="#http">HTTP</a></li>
              <li>
                <a href="#static-ip">IP & Static IP</a>
                <ul>
                  <li><a href="#metasploitable-static-ip-configuration">Metasploitable Static IP Configuration</a></li>
                  <li><a href="#windows-static-ip-configuration">Windows Static IP Configuration</a></li>
                  <li><a href="#ubuntu-server-static-ip-configuration">Ubuntu Server Static IP Configuration</a></li>
                </ul>
              </li>
              <li><a href="#broadcasting">Broadcasting</a></li>
              <li><a href="#dhcp">DHCP</a></li>        
              <li><a href="#router">Router</a></li>
              <li><a href="#switch">Switch</a></li>
              <li><a href="#gateway">Gateway</a></li>  
              <li><a href="#ftp">FTP</a></li>
              <li><a href="#tcp-handshake">TCP Handshake</a></li>    
      </ul>
    </li>
    <li>
      <a href="#setting-up">Setting Up</a>
    </li>
    <!-- <li><a href="#contributing">Contributing</a></li> -->
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

The DHCP Server for Ubuntu with PFsense Firewall is a project designed to provide efficient and reliable dynamic IP address allocation within your network infrastructure. This system combines the power and flexibility of Ubuntu Server, a widely used Linux distribution, with the robust security features of PFsense, a popular open-source firewall.


The primary purpose of this project is to simplify the management and distribution of IP addresses within your network. The Dynamic Host Configuration Protocol (DHCP) server automates the process of assigning IP addresses, subnet masks, default gateways, and other network configuration parameters to devices connected to your network. By automating this process, it eliminates the need for manual configuration on each individual device, saving time and reducing the potential for human error.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

This project was built using the following components:

* [![ubuntu][ubuntu]][ubuntu-url]
* [![windows][windows]][windows-url]
* [![linux][linux]][linux-url]
* [![pfsense][pfsense]][pfsense-url]
* [![metasploitable][metasploitable]][metasploitable-url]
* [![virtualbox][virtualbox]][virtualbox-url]






<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

The DHCP server setup in this project includes the configuration of three separate LANs. Within one of these LANs, an IP block of 30.30.30.2 is allocated, the Ubuntu Server acts as the DHCP server, and a static IP address of 30.30.30.3 is assigned. PFsense firewall runs on IP address 10.0.10.10.2.

The purpose of this setup is to enable Ubuntu Server to distribute IP addresses from 30.30.30.3 range to devices connected to other LANs. With the implementation of this DHCP server solution, IP address allocation becomes automatic, eliminating the need for manual configuration on each device.

It is important to note that with this DHCP server setup, broadcasting from one LAN to another is not directly possible. A DHCP relay agent is used to facilitate the distribution of IP addresses over multiple LANs.

A DHCP relay agent, also known as a DHCP helper, is configured on routers or layer 3 switches that connect LANs. This agent receives DHCP broadcast messages from devices on a LAN and forwards them to the DHCP server located on Ubuntu Server's LAN (30.30.30.3). The DHCP server then responds with the appropriate IP address assignments, and the relay agent forwards these responses back to the requesting devices on their LANs.


### Prerequisites

To install the required files for the DHCP server and FTP, please enter the following commands into your terminal in Ubuntu-server: 
* pip
  ```sh
  sudo apt-get install isc-dhcp-server
  ```
  ```sh
  sudo apt-get install vsftpd
  ```


### Installation

_Setting up the DHCP Server and FTP on Ubuntu Server requires downloads and installations._

1. Download VirtualBox
2. Download Ubuntu Server from the link below
   ```sh
   https://ubuntu.com/server
   ```
3. Download Windows10 for VirtualBox
   ```sh
   https://drive.google.com/file/d/1YKnn1bzbC_34oEX91Vxj5BB1GdmWW3tP
   ```
   _Note: Windows10 image is not provided anymore by Microsoft, you can download it from the link above._

4. Download PFSense for VirtualBox
   ```sh
    https://www.pfsense.org/download/
   ```

5. Download Metasploitable for VirtualBox
   ```sh
    https://sourceforge.net/projects/metasploitable/
   ```

6. Configure the RAM and GPU for the virtual machines.
   ```js
   That's it! You're now ready to start setting up your DHCP server.
   ```

  _Note: For Windows, you must give at least 2 GB of RAM for it to work properly._

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- Terminology -->

## Terminology

Before we begin the setup of our DHCP and FTP server, we need to understand some terms.

### Network

A network consists of two or more computers connected together to share resources (such as printers and CDs), exchange files, or allow electronic communication. Computers in a network can be connected via cables, telephone lines, radio waves, satellites, or infrared light beams.

### LAN and Subnet

LAN (Local Area Network) refers to a group of devices connected within a specific physical location or network segment. It usually represents a single network infrastructure that allows devices to communicate directly with each other.

A subnet (subnet), on the other hand, is the division of a larger network into smaller logical networks. It enables better organization and management of IP addresses by grouping devices based on network requirements, security policies, or other factors.

Without proper routing between subnets, devices on one subnet cannot communicate directly with devices on the other subnet.

In our project 10.10.10.0/24 , 20.20.20.0/24 and 30.30.30.0/24 
are the subnets of our LAN.


### DNS

A Domain Name System (DNS) turns domain names into IP addresses that allow browsers to access websites and other internet resources. Every device on the Internet has an IP address that other devices can use to locate the device. Rather than memorizing a long list of IP addresses, people can simply enter the website name and DNS will get the IP address for them.

### HTTP

Hypertext Transfer Protocol (HTTP) is the foundation of the World Wide Web and is used to load web pages using hypertext links. HTTP is an application layer protocol designed to transfer information between networked devices and runs on top of other layers of the network protocol stack. A typical flow over HTTP involves a client machine making a request to a server and the server then sending a response message.
### Static IP

IP address means internet protocol address; An identifying number associated with a particular computer or computer network. When connected to the Internet, the IP address allows computers to send and receive information. Every device has its own unique IP address.

There are four different types of IP addresses: public, private, static, and dynamic. Public and private indicates the location of the network while static and dynamic indicates the permanency of the IP Address.

A static IP address is the one that is created manually and does not change over time. But, when establishing a network suppose you have 200 computers. You'd have to configure all the IP addresses, subnet-masks, and default gateway. And also these configurations differs from one operating system to another. Below you can see how static IP configurations are made on different operating systems.

<!-- 
    IDS:
     metasploitable-static-ip-configuration
     windows-static-ip-configuration
     ubuntu-server-static-ip-configuration
  -->
#### Metasploitable Static IP Configuration

[![metasploitable-static][metasploitable-static]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)


#### Windows Static IP Configuration

_Control Panel -> Network and Internet -> Network and Sharing Center_

[![windows-static][windows-static]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Note that default gateway should be PFSense in our case since we are using firewall (in our case 10.10.10.2)_

[![windows-static][windows-static-2]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)


#### Ubuntu Server Static IP Configuration

_/etc/netplan/00-installer-config.yaml_

[![ubuntu-server-static][ubuntu-server-static]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

### Broadcasting

Broadcasting is a type of group communication in which a sender provides data to multiple receivers at the same time. This is a communication model where each sending device sends data to all other devices in the network area.

When your computer first connects to a Local Area Network (LAN), it does not have an IP address. It must connect to a Dynamic Host Configuration Protocol (DHCP) server to obtain an IP address. To do this, your computer must perform a broadcast to a private Broadcast IP address of 255.255.255.255; this essentially means that every machine on the LAN will receive your request for an IP address. The DHCP server will respond with an IP address to be assigned to your machine.

In our case we will specify the broadcast address of LAN's as 10.10.10.255, 20.20.20.255, 30.30.30.255 meaning that the machines on these subnets will broadcast for IP address


_Metasploitable machine Broadcasting for getting IP_

[![before-getting-ip][before-getting-ip]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Refreshing networking service to get IP_

   ```sh
    /etc/init.d/networking restart
   ```


[![getting-ip][getting-ip]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Metasploitable machine after getting its IP from DHCP Server_

[![after-getting-ip][after-getting-ip]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

### DHCP

Dynamic Host Configuration Protocol (DHCP) is a network protocol used to automate the process of configuring devices on IP networks.

[![dhcp_server_running][dhcp_server_running]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

### Router


### Switch


### Gateway



### FTP


### TCP Handshake


<!-- Setting Up -->
## Setting Up

[![Screen Shots][parking-spaces-to-be-checked]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Places that are considered as parking spaces manually selected with ParkingSpacePicker.py_


<tr>
    <td>
      <img src="readme-images/single-parking-frame.png"></img>
    </td>
    <td>
      <img src="readme-images/single-parking-frame-without-rectangle.png"></img>
    </td>
    
</tr>

_After selecting the parking spaces, storing them into CarParkPos file and splitting each frame that are selected with ParkingSpacePicker.py_

[![Screen Shots][blurred-img]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Blurring the image after making it grayscale_

[![Screen Shots][threshold-img]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Converting image into a binary image with Thresholding_

[![Screen Shots][dilated-img]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_After thresholding, to remove unwanted white pixels we are dilating the threshold image_

[![Screen Shots][median-img]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_To adjust the thickness, we're generating the median image_

<tr>
    <td>
      <img src="readme-images/single-frame-after-dilation-empty-space.png">
      </img>
    </td>
    <td>
      <img src=" readme-images/single-frame-after-dilation-car-parked.png">
      </img>
    </td>
</tr>

_After dilation and median images, it's evident whether there's a car in a parking spot or not._

[![Screen Shots][spaces-with-counters]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Now, on our original dilated image, we can count the white pixels and display their numbers on the image. If a parking space is empty, the number of white pixels is expected to be less than 900. However, if the number of white pixels is more than 900, it is an indication that there is a car present in the parking space._

[![Screen Shots][product-screenshot]](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

_Finally, we count the number of available parking spaces and draw rectangles around each parking spot. If a parking space is available, we mark it with a green color, and if it is occupied, we mark it with a red color._

See the [main.py](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/blob/master/main.py) for the detailed explanations on the code.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Bayram Alper KILIÇ - [@alperrkilic](https://www.linkedin.com/in/bayram-alper-kilic/) - alperkilicbusiness@gmail.com

Project Link: [https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense](https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Creating a project like the Parking Space Counter requires a lot of research, experimentation, and dedication. I would like to take this opportunity to acknowledge and thank the many individuals, channels, and websites that helped me along the way. Without their guidance and support, this project would not have been possible. In particular, I would like to recommend the following channels and websites for their invaluable resources and contributions to the field of computer vision and image processing.

* [Computer Vision Zone](https://www.computervision.zone/)
* [Murtaza's Workshop - Robotics and AI](https://www.youtube.com/@murtazasworkshop)
* [ChatGPT](https://chat.openai.com/chat)
* [Choose an Open Source License](https://choosealicense.com)
* [Img Shields](https://shields.io)


<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- Shields & URLS -->

[contributors-shield]: https://img.shields.io/github/contributors/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[contributors-url]: https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[forks-url]: https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/network/members
[stars-shield]: https://img.shields.io/github/stars/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[stars-url]: https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/stargazers
[issues-shield]: https://img.shields.io/github/issues/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[issues-url]: https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/issues
[license-shield]: https://img.shields.io/github/license/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[license-url]: https://github.com/alperrkilic/DHCP-FTP-Server-with-PFSense/blob/master/LICENSE.txt

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/bayram-alper-kilic/
[ubuntu]: https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white
[ubuntu-url]: https://ubuntu.com/
[windows]: https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white
[windows-url]: https://www.microsoft.com
[linux]: https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black
[linux-url]: https://www.linux.org/
[pfsense]: https://img.shields.io/badge/PFSense-000000?style=for-the-badge&logo=pfsense&logoColor=white
[pfsense-url]: https://www.pfsense.org/
[metasploitable]: https://img.shields.io/badge/Metasploitable-000000?style=for-the-badge&logo=metasploitable&logoColor=white
[metasploitable-url]: https://docs.rapid7.com/metasploit/metasploitable-2-exploitability-guide/
[virtualbox]: https://img.shields.io/badge/VirtualBox-00000?style=for-the-badge&logo=virtualbox&logoColor=white&color=blue
[virtualbox-url]: https://www.virtualbox.org/

<!-- Images -->

<!-- Static IP section -->

[metasploitable-static]: readme-images/Static-IP/metasploitable_static_ip.png
[windows-static]: readme-images/Static-IP/windows_static_ip_1.png
[windows-static-2]: readme-images/Static-IP/windows_static_ip_2.png
[ubuntu-server-static]: readme-images/Static-IP/ubuntu-server-static-ip.png


<!-- Broadcasting -->

[before-getting-ip]: readme-images/DHCP/Working/before_getting_ip.png
[getting-ip]: readme-images/DHCP/Working/getting_ip.png
[after-getting-ip]: readme-images/DHCP/Working/after_getting_ip.png

<!-- DHCP -->

[dhcp_server_running]: readme-images/DHCP/Working/dhcp_server_running.png


[product-screenshot]: readme-images/DHCP/Working/PFSense-connection.png
[single-parking-frame]: readme-images/single-parking-frame.png
[single-no-rectangle]: readme-images/single-parking-frame-without-rectangle.png
[blurred-img]: readme-images/Blurred-image.png
[threshold-img]: readme-images/Threshold-image.png
[dilated-img]: readme-images/Dilated-thicker-image.png
[median-img]: readme-images/Median-image.png
[single-dilated-parked]: readme-images/single-frame-after-dilation-car-parked.png
[single-dilated-empty]: readme-images/single-frame-after-dilation-empty-space.png
[spaces-with-counters]: readme-images/Spaces-with-counted-pixels.png
[parking-spaces-to-be-checked]: readme-images/parking-spaces-to-be-checked.png
