# Network Topology with Mininet

This repository is lab for NCTU course "Introduction to Computer Networks 2018".

---

## Abstract

In this lab, we are going to write a Python program which can generate a network topology using Mininet and use iPerf to measure the bandwidth of the topology.

---
## Objectives

1. Learn how to create a network topology with Mininet
2. Learn how to measure the bandwidth in your network topology with iPerf

---
## Execution

> TODO: 
>* Describe how to execute your program
 
  First, execute "topology.py". If there is no error message, it will display many things. For example, it will show the hosts and         switches you created.Furthermore, every links and their states between hosts and switches wil be display. 
  
  After displaying data, the program will enter CLI(Command Line Interface). Then, we use iperf to test the link state.  
 
> * Show the screenshot of using iPerf command in Mininet
 
![](https://i.imgur.com/zHjdjuz.png)

![](https://i.imgur.com/840e0mI.png)



---
## Description

### Mininet API in Python

> TODO:
> * Describe the meaning of Mininet API in Python you used in detail
> >
 There are many function we use in the python code. First, we use **"setLogLevel"** to set Mininet's output level and use **Mininet(topo, controller, link)** to create mininet object and manage. Second, we override the **"build()"** functoin to create our own topology in the class **"MyTopo"**.In the build function, we use function **"addSwitch", "addHost", "addLink"** to complete the topology we want by building every Host, Switch, and Link.
 
 Now, we already have a complete topology and it is ready to emulate. First, we use **"start()"** to start network. Then, we use **"dumpnodeconnection()"** to dump connection from nodes, and use **"pingall()"** to test the connectivity between every node. Last but not least, we open CLI to get more detailed information by using iperf commands.    

### iPerf Commands

> TODO:
> * Describe the meaning of iPerf command you used in detail
>
  I used **"h4 iperf -s -u -i 1 > ./out/result &"** and **"h2 iperf -c 10.0.0.4 -u -i 1"** these two commands.
First, **"h4" and "h2"** means the host we want to use. **"-s", "-c"** indicate that the host is server or client mode. The parameter after -c **"10.0.0.4"** is the host that client wants to connect.  **"-u"** means run in UDP, not TCP. **"-i 1"** means the interval should be set to 1s. 

Second, **">  ./out/result"** means that save the iperf report to the destination we assign. **"&"** means the command haven't finished, we want to add something else. 

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

