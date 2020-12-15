# NCTU-Computer-Network


# Lab1: Packet Manipulation

This repository is lab for NCTU course "Introduction to Computer Networks 2018".

---
## Abstract

In this lab we are going to learn how to use Scapy - a powerful interactive packet manipulation program, which can forge or decode packets of a wide number of protocols, send them on wire, capture them, match requests and replies, and much more. By using Scapy, we are going to define our own protocol to compute Fibonacci number through packets sending and receiving.

---
## Objectives

This lab aims to learn how we use Scapy and Python to program a simple network protocol and observe the behavior of packet sending and receiving via Wireshark.

1. Basic knowledge of Docker
2. Linux networking
3. Python with Scapy
4. Wireshark
5. Git & GitHub

---
## Tasks

* In lab course (Oct. 11 @EC-315, 316)
    1. Environment Setup
    2. Define protocol via Scapy
    3. Send packets
    4. Sniff packets
    5. Run sender and receiver
    6. Push your files to remote
* Homework
    1. Load PCAP via Wireshark
    2. Filter the target packet
    3. Decode the secret key
    4. Report

---
## Authors

* [David Lu](https://github.com/yungshenglu)

> This repository is inspired by [Kevin Cyu](https://github.com/kevinbird61). He gave me lots of advices and supports during preparation.

## License

GNU GENERAL PUBLIC LICENSE Version 3


# Lab2: Network Topology with Mininet

This repository is lab for NCTU course "Introduction to Computer Networks 2018".

---

## Abstract

In this lab, we are going to write a Python program which can generate a network topology using Mininet and use iPerf to measure the bandwidth of the topology.

---
## Objectives

1. Learn how to create a network topology with Mininet
2. Learn how to measure the bandwidth in your network topology with iPerf

---

### Tasks

> TODO:
> * Describe how you finish this work step-by-step in detail


1. **Environment Setup**

    This step is easy because Lab1 did the same thing before. First, we join the Lab2-class and connect to the docker container. Furthermore, clone your lab2 assignment to your container to modify. Last, try command "mn" to test if we can execute it successfully. Then we finished the first step.   

2. **Example of Mininet**

    In the file we clone from github-Lab2, there is a file named "example.py". Step 2 is mainly to test if we can execute the program successfully. "example.py" is a basic topology that one controller, one switch, and two host that connect to the switch.

    After executing "example.py", we get some useful information such as the host and switch we create and links between host and switch. Furthermore, we can see every links' state. In this case, there is no missing packet. Last but not least, if we met the error "...File exists", we input the command **"[sudo]mn -c"** to clear. If we understand the program "example.py", then we go to the next step.  

3. **Topology Generator**

    Step 3, First, find out the correct topology picture we need. In my case, I get **0616225mod3 = 1**, so I use **topo1 picture** as my Lab2. 

    Second, we should write a python program to simulate the topo1.picture shown below. ![](https://i.imgur.com/bWLreAr.png)
    We can refer to example.py to finish our program named "topology.py". 
Actually, it is not difficult if we understand every code in "example.py". All we need to modify is add host, switch, link respcetively and set parameters such as delay, bandwidth, and loss according to topology picture1. Furthermore, add function dumpnodeconnection() and CLI() to get more detailed information. 
If we met the same error "...File exists", refer to the troubleshooting above. 
After finishing "topology.py", we can go to the last step. 

4. **Measurement**

    The last step is to use "iperf" command to measure the topology we build. According to the introduction to LAB2, we connect host4(server) and host2(client) to measure the connectivity between them in this topology. After testing my topology, I get the similar outcome with the outcome the introduction provided. Furthermore, the command we type will send the final report to a folder we assign. We can check whether the outcome is similar to the outcome introduction provieded. If they are similar, we get the correct outcome and finish Lab2. 

---
## References

> TODO: 
> * Please add your references in the following
* **Markdown CheatSheet**
    * [Markdown 語法說明](https://markdown.tw/#p)
    * [Markdown Guide-Basic Syntex](https://www.markdownguide.org/basic-syntax)
    * [HackMd ](https://hackmd.io/s/features-tw#tags-%E5%8A%9F%E8%83%BD-%E9%85%B7-%E6%9B%B4%E6%96%B0)
* **Mininet**
    * [Mininet Walkthrough](http://mininet.org/walkthrough/)
    * [Introduction to Mininet](https://github.com/mininet/mininet/wiki/Introduction-to-Mininet)
    * [Mininet Python API Reference Manual](http://mininet.org/api/annotated.html)
    * [A Beginner's Guide to Mininet](https://opensourceforu.com/2017/04/beginners-guide-mininet/)
    * [GitHub/OSE-Lab - 熟悉如何使用 Mininet](https://github.com/OSE-Lab/Learning-SDN/blob/master/Mininet/README.md)
    * [菸酒生的記事本 – Mininet 筆記](https://blog.laszlo.tw/?p=81)
    * [Hwchiu Learning Note – 手把手打造仿 mininet 網路](https://hwchiu.com/setup-mininet-like-environment.html)
    * [阿寬的實驗室 – Mininet 指令介紹](https://ting-kuan.blog/2017/11/09/%E3%80%90mininet%E6%8C%87%E4%BB%A4%E4%BB%8B%E7%B4%B9%E3%80%91/)
    * [Mininet 學習指南](https://www.sdnlab.com/11495.html)
* **Python**
    * [Python 2.7.15 Standard Library](https://docs.python.org/2/library/index.html)
    * [Python Tutorial - Tutorialspoint](https://www.tutorialspoint.com/python/)
* **Others**
    * [iPerf3 User Documentation](https://iperf.fr/iperf-doc.php#3doc)
    * [Cheat Sheet of Markdown Syntax](https://www.markdownguide.org/cheat-sheet)
    * [Vim Tutorial – Tutorialspoint](https://www.tutorialspoint.com/vim/index.htm)
    * [鳥哥的 Linux 私房菜 – 第九章、vim 程式編輯器](http://linux.vbird.org/linux_basic/0310vi.php)

---
## Contributors

> TODO:
> * Please replace "YOUR_NAME" and "YOUR_GITHUB_LINK" into yours

* [NCTU193](https://github.com/NCTU193)
* [David Lu](https://github.com/yungshenglu)

---
## License

GNU GENERAL PUBLIC LICENSE Version 3


# Lab3: Route Configuration
 
 This repository is a lab for NCTU course "Introduction to Computer Networks 2018".
 
 ---
 ## Abstract
 
 In this lab, we are going to write a Python program with Ryu SDN framework to build a simple software-defined network and compare the different between two forwarding rules.
 
 ---
 ## Objectives
 
 1. Learn how to build a simple software-defined networking with Ryu SDN framework
 2. Learn how to add forwarding rule into each OpenFlow switch
 
---
## Description

### Tasks


**1. Environment Setup**

This Step is the easiest. I first joined the class in Github and successfully connected to my containter with putty. After that, I clone the lab3 document from github then try to run mininet. When I try to execute mininet, I met some error. However, I followed the troubleshooting in slides and solved the problem.  

**2. Example of Ryu SDN**

In Task2, I follow the slides running `SimpleTopo.py` with mininet, and then open another terminal to execute `SimpleController.py`. After doing Task2, I realize that these two files are relevant. `SimpleController.py` can affect `SimpleTopo.py` using Ryu command. 
 
**3. Mininet Topology**

 Task3 started to enter the main topic of Lab3. First, I modified `SimpleTopo.py`, add some constraint between links refer to `topo.png` and save as `topo.py`. Because of the experience of Lab2, I didn't meet problem in task3.  
 
 **4. Ryu Controller**
 
 In Task4, I modified `SimpleController.py` and save as `controller.py`. After observing `SimpleController.py` carefully, I realize that the code we should modified in `controller.py` is the port number. We should modified the port number of links between switches and hosts according to **the picture's forwarding rules in slides page 35**. As for how did I know the port number of every links? I observed that there are some information in `topo.py`. When creating every links in `topo.py`, it added the source port number and destination port nubmer. Furthermore, we can type `links` in minnet CLI, it will show that every links' state and the port numbers they use. With these information, I finished the Task4.   
 
 **5. Measurement**
 
 In Task5, First I execute `topo.py` using mininet in one terminal and execute `SimpleController.py` using ryu-manager in another terminal. Then, I input iperf command in mininet CLI in `topo.py`. The iperf command are used to measure the connection condtion between host1 and host2. After finishing measurement, I execute `topo.py` again. Then, I execute `controller.py` in another terminal and then using iperf command in mininet CLI. After measuring, I got two results of connection condition of different forwarding rules. Then I can compare their difference.  

---
## References

* **Ryu SDN**
    * [IP協定wiki](https://en.wikipedia.org/wiki/List_of_IP_protocol_numbers)
    * [開始使用Ryu](https://ryu-zhdoc.readthedocs.io/getting_started.html)
    * [Ryubook Documentation](https://osrg.github.io/ryu-book/en/html/)
    * [Ryubook [PDF]](https://osrg.github.io/ryu-book/en/Ryubook.pdf)
     * [Ryu 4.30 Documentation](https://github.com/mininet/mininet/wiki/Introduction-to-Mininet)
     * [Ryu Controller Tutorial](http://sdnhub.org/tutorials/ryu/)
     * [OpenFlow 1.3 Switch Specification](https://www.opennetworking.org/wp-content/uploads/2014/10/openflow-spec-v1.3.0.pdf)
     * [Ryubook 說明文件](https://osrg.github.io/ryu-book/zh_tw/html/)
     * [GitHub - Ryu Controller 教學專案](https://github.com/OSE-Lab/Learning-SDN/blob/master/Controller/Ryu/README.md)
     * [Ryu SDN 指南 – Pengfei Ni](https://feisky.gitbooks.io/sdn/sdn/ryu.html)
     * [OpenFlow 通訊協定](https://osrg.github.io/ryu-book/zh_tw/html/openflow_protocol.html)
 * **Python**
     * [Python 2.7.15 Standard Library](https://docs.python.org/2/library/index.html)
     * [Python Tutorial - Tutorialspoint](https://www.tutorialspoint.com/python/)
 * **Others**
     * [Cheat Sheet of Markdown Syntax](https://www.markdownguide.org/cheat-sheet)
     * [Vim Tutorial – Tutorialspoint](https://www.tutorialspoint.com/vim/index.htm)
     * [鳥哥的 Linux 私房菜 – 第九章、vim 程式編輯器](http://linux.vbird.org/linux_basic/0310vi.php)
 
 ---
## Contributors

<!-- > TODO:
> * Please replace "YOUR_NAME" and "YOUR_GITHUB_LINK" into yours
> * Please replace "`YOUR_NAME`" and "`YOUR_GITHUB_LINK`" into yours -->
* [張承遠](https://github.com/NCTU193)
* [David Lu](https://github.com/yungshenglu)
 
 ---
 ## License
 
 GNU GENERAL PUBLIC LICENSE Version 3


