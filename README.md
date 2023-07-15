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
  <a href="https://github.com/alperrkilic/Parking-Space-Counter-Project">
    <img src="readme-images/DHCP_1.png" alt="Logo" width="100" height="100">
  </a>

  <h3 align="center">How to set up a DHCP Server with PFSense</h3>

  <p align="center">
    A Simple Network Project 
    <br />
    <a href="https://github.com/alperrkilic/Parking-Space-Counter-Project"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/alperrkilic/Parking-Space-Counter-Project">View Demo</a>
    ·
    <a href="https://github.com/alperrkilic/Parking-Space-Counter-Project/issues">Report Bug</a>
    ·
    <a href="https://github.com/alperrkilic/Parking-Space-Counter-Project/issues">Request Feature</a>
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
    <!-- <li><a href="#usage">Usage</a></li> -->
    <li><a href="#setting-up">Setting Up</a></li>
    <!-- <li><a href="#contributing">Contributing</a></li> -->
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

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

The DHCP server setup in this project involves the configuration of three separate LANs. Within one of these LANs, an IP block of 30.30.30.2 is allocated, with the Ubuntu Server acting as the DHCP server and assigned a static IP address of 30.30.30.3. The PFsense firewall operates on the IP address 10.10.10.2.

The purpose of this setup is to enable the Ubuntu Server to distribute IP addresses from the 30.30.30.3 range to the devices connected to the other LANs. By implementing this DHCP server solution, IP address allocation becomes automated, eliminating the need for manual configuration on each device.

In this DHCP server setup, it is important to note that broadcasting from one LAN to another LAN is not directly possible. To facilitate the distribution of IP addresses across the multiple LANs, a DHCP relay agent is used.

A DHCP relay agent, also known as a DHCP helper, is configured on the routers or layer 3 switches connecting the LANs. This agent receives DHCP broadcast messages from devices in one LAN and forwards them to the DHCP server located in the Ubuntu Server's LAN (30.30.30.3). The DHCP server then responds with the appropriate IP address assignments, and the relay agent forwards these responses back to the requesting devices in their respective LANs.



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



<!-- Setting Up -->
## Setting Up

[![Screen Shots][parking-spaces-to-be-checked]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

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

[![Screen Shots][blurred-img]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

_Blurring the image after making it grayscale_

[![Screen Shots][threshold-img]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

_Converting image into a binary image with Thresholding_

[![Screen Shots][dilated-img]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

_After thresholding, to remove unwanted white pixels we are dilating the threshold image_

[![Screen Shots][median-img]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

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

[![Screen Shots][spaces-with-counters]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

_Now, on our original dilated image, we can count the white pixels and display their numbers on the image. If a parking space is empty, the number of white pixels is expected to be less than 900. However, if the number of white pixels is more than 900, it is an indication that there is a car present in the parking space._

[![Screen Shots][product-screenshot]](https://github.com/alperrkilic/Parking-Space-Counter-Project)

_Finally, we count the number of available parking spaces and draw rectangles around each parking spot. If a parking space is available, we mark it with a green color, and if it is occupied, we mark it with a red color._

See the [main.py](https://github.com/alperrkilic/Parking-Space-Counter-Project/blob/master/main.py) for the detailed explanations on the code.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Bayram Alper KILIÇ - [@alperrkilic](https://www.linkedin.com/in/bayram-alper-kilic/) - alperkilicbusiness@gmail.com

Project Link: [https://github.com/alperrkilic/Parking-Space-Counter-Project](https://github.com/alperrkilic/Parking-Space-Counter-Project)

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

[contributors-shield]: https://img.shields.io/github/contributors/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[contributors-url]: https://github.com/alperrkilic/Parking-Space-Counter-Project/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[forks-url]: https://github.com/alperrkilic/Parking-Space-Counter-Project/network/members
[stars-shield]: https://img.shields.io/github/stars/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[stars-url]: https://github.com/alperrkilic/Parking-Space-Counter-Project/stargazers
[issues-shield]: https://img.shields.io/github/issues/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[issues-url]: https://github.com/alperrkilic/Parking-Space-Counter-Project/issues
[license-shield]: https://img.shields.io/github/license/alperrkilic/Parking-Space-Counter-Project.svg?style=for-the-badge
[license-url]: https://github.com/alperrkilic/Parking-Space-Counter-Project/blob/master/LICENSE.txt

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
