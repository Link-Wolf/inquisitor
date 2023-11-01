<div id="top"></div>

<div align="center">
 <a href="https://github.com/Link-Wolf/inquisitor" title="Go to GitHub repo"><img src="https://img.shields.io/static/v1?label=Link-Wolf&message=inquisitor&color=blue&logo=github&style=for-the-badge" alt="Link-Wolf - inquisitor"></a>
 <a href="https://"><img src="https://img.shields.io/badge/42_grade-125%2F_100-brightgreen?style=for-the-badge" alt="42 grade - 125 / 100"></a>
 <a href="https://"><img src="https://img.shields.io/badge/Year-2022-ffad9b?style=for-the-badge" alt="Year - 2022"></a>
 <a href="https://github.com/Link-Wolf/inquisitor/stargazers"><img src="https://img.shields.io/github/stars/Link-Wolf/inquisitor?style=for-the-badge&color=yellow" alt="stars - inquisitor"></a>
 <a href="https://github.com/Link-Wolf/inquisitor/network/members"><img src="https://img.shields.io/github/forks/Link-Wolf/inquisitor?style=for-the-badge&color=lightgray" alt="forks - inquisitor"></a>
 <a href="https://github.com/Link-Wolf/inquisitor/issues"><img src="https://img.shields.io/github/issues/Link-Wolf/inquisitor?style=for-the-badge&color=orange" alt="issues - inquisitor"></a>
 <a href="https://www.linux.org/" title="Go to Linux homepage"><img src="https://img.shields.io/badge/OS-linux-blue?logo=linux&logoColor=white&style=for-the-badge&color=9cf" alt="OS - linux"></a>
</div>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a>
    <img src="https://www.42mulhouse.fr/wp-content/uploads/2022/06/logo-42-Mulhouse-white.svg" alt="Logo" width="192" height="80">
  </a>

  <h3 align="center">Piscine Cybersecurity - inquisitor</h3>

  <p align="center">
   <em>ARP Poisoning</em><br/>
    A prototype of an ARP poisoning program
    <br />
    <br />
    <a href="https://github.com/Link-Wolf/inquisitor/issues">Report Bug</a>
    ·
    <a href="https://github.com/Link-Wolf/inquisitor/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#goal">Goal</a>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage-examples">Usage examples</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

<!-- GOAL -->
## Goal

<div align="center">
  <a>
	<img src="https://www.veracode.com/sites/default/files/2021-07/veracode-appsec_man-middle-attack.png" alt="inquisitor">
  </a>
</div>
</br>

This cybersecurity project aims to emulate a classical Man in the Middle attack by ARP poisoning in a controlled environment. The goal is to be able to intercept the traffic between a client and a FTP server and to be able to read the packets sent by the client to the server and vice versa.

Since it's only a prototype, the `poisoner` isn't well hidden –actually, the `target` ­can see the changes when it occurs– and the `poisoner` only intercepts FTP packets.
> The program is written in C++


<p align="right">(<a href="#top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started


### Prerequisites

Having [Docker](https://docker.com) installed on your system and be able to run the `docker compose` command on your system


### Installation

1. Clone the repo

   ```sh
   $> git clone https://github.com/Link-Wolf/inquisitor.git
   ```

2. Launch the containers
	
   ```sh
   $> cd inquisitor
   $> make
   ```

3. From the poisoner

   ```sh 
   $> docker exec -it poisoner bash
   #> inquisitor [-v] IP_src MAC_src IP_target MAC_target
   ```
   > The `-v` (verbose) option is used to display the packets sent and received by the program
   > The `IP_src` and `MAC_src` are the IP and MAC addresses of the FTP server
   > The `IP_target` and `MAC_target` are the IP and MAC addresses of the victim

3. From the target

	```sh
	$> docker exec -it target bash
	#> ftp source
	> ls|get FILE|pwd|... 
	```
	> Source is the hostname of the FTP server
	> FILE is the name of the file to download




<p align="right">(<a href="#top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->
## Usage examples

#### Using the `target` container as a simple client that connect to a FTP server

![](https://cdn.discordapp.com/attachments/907303542438629406/1130439179914973274/image.png)

#### Using the `poisoner` container to perform a MITM (Man In The Middle) attack on the `target` container

![](https://cdn.discordapp.com/attachments/907303542438629406/1130439387038101514/image.png)

In this example, the `poisoner` container intercepts the FTP packets at the moment the `target` tries to download a file named `my_awesome_file.exe`.

<p align="right">(<a href="#top">back to top</a>)</p>


<!-- CONTRIBUTING -->
## Contributing

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- CONTACT -->
## Contact

Mail : xxxxxxx@student.42mulhouse.fr

Project Link: [https://github.com/Link-Wolf/inquisitor](https://github.com/Link-Wolf/inquisitor)

<p align="right">(<a href="#top">back to top</a>)</p>
