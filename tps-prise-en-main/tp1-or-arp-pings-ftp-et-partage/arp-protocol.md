# 🪱 ARP Protocol

## ARP (_Address Resolution Protocol_)

{% hint style="info" %}
**ARP is used to match local MAC adresses to network IP adresses**
{% endhint %}

The goal of ARP is to have kind of a **"whitelist"** of machines that are know to be part of the network. It is considered to be a **"secure"** way of permitting and banning non-permitted computers from the network. But it also has its downsides : you can use a "virtual" MAC address to _spoof_ your computer, using the MAC address of a computer belonging to the whitelist.

When a machine is searching for another machine in the network, it uses **ARP-broadcast** to ask to every machine in the network **if their MAC address matches with the IP address that it uses**.\
If a machine has the _**corresponding IP address**_, it answers the ARP request and the sending machine registers the link between the network IP address and the physical MAC address, allowing the two machines to communicate with each other.

{% hint style="warning" %}
ARP was a main _vulnerability_ in the past : the main flaw with ARP is that it allows basically everyone to answer an ARP request and get recognized as a machine that it is not; any link between an IP address and a MAC address is cached in the machine emitting the ARP request.\
\
This type of attack is called _**ARP-poisoning**_. It uses a MITM (Man In The Middle) tactic : \
<mark style="background-color:red;">one</mark> can answer <mark style="background-color:purple;">Computer A</mark>'s ARP request and act like <mark style="background-color:orange;">Computer B</mark> and do the same by answering <mark style="background-color:orange;">Computer B</mark>'s ARP request and act like <mark style="background-color:purple;">Computer A</mark>.

Therefore, when <mark style="background-color:purple;">Computer A</mark> thinks it talks with <mark style="background-color:orange;">Computer B</mark> but actually talks with the <mark style="background-color:red;">pirate</mark>, allowing him to intercept everything that is sent to Computer B.\

{% endhint %}
