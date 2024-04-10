<h1>Implementing Juice Shop, a Vulnerable Web App on Amazon AWS</h1>

<h2>Description</h2>
Juce Shop is a vulnerable web app, similar to a CTF that aspiring pen testers can use to test their skills. In this projcet we setup Juice Shop on a VPC using Amazon AWS. We have the option of creating an instance in either a private or public subnet, which affects our security. 

For this project we:
<ul>
  <li>Create a Region, VPC, Subnet, and Secuirity Group in AWS.</li>
  <li>Launch an EC2 instance in a private subnet.</li>
  <li>Configure our internet gateway and route table to allow our SSH connection.</li>
  <li>Install and start Docker on our virtual machine. </li>
  <li>Install node.js then Juice Shop onto our virtual machine.</li>  
</ul>
<br />


<h2>Platforms and Technologies Used</h2>

- <b>Amazon AWS</b> 
- <b>EC2 Virtual Machines</b>
- <b>Docker</b>


<p align="center">
Juce Shop initialized: <br/>
<img src="https://i.imgur.com/7ZZDg4I.png" height="80%" width="80%"/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
