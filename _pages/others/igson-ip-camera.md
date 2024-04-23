---
title: "Hacking and configuring IP Camera IGSON V-IPW42-2SN-POE "
permalink: /pages/others/ignison-v-ipw42-2sn-ip-camera
sidebar:
  title: "Others:"
  nav: sidebar-others
layout: single
defaults:
  # _posts
  - scope:
      path: ""
      type: others
---

I found this IP camera on junkyard
<!--
<img src="/assets/pages/others/igson-ip-camera/camera-igson_1.jpg" alt="Tekst alternatywny" style="width:300px">
<br>
<img src="/assets/pages/others/igson-ip-camera/camera-igson_2.jpg" alt="Tekst alternatywny" style="width:300px">
<br>
<img src="/assets/pages/others/igson-ip-camera/camera-igson_3.jpg" alt="Tekst alternatywny" style="width:300px">
<br>
<img src="/assets/pages/others/igson-ip-camera/camera-igson_4.jpg" alt="Tekst alternatywny" style="width:300px">
<br>
<img src="/assets/pages/others/igson-ip-camera/camera-igson_5.jpg" alt="Tekst alternatywny" style="width:300px">
<br>
<img src="/assets/pages/others/igson-rj45.jpg" alt="Tekst alternatywny" style="width:300px">
--->



<figure class="half">
    <a href="/assets/pages/others/igson-ip-camera/camera-igson_1.jpg"><img src="/assets/pages/others/igson-ip-camera/camera-igson_1.jpg"></a>
    <a href="/assets/pages/others/igson-ip-camera/camera-igson_4.jpg"><img src="/assets/pages/others/igson-ip-camera/camera-igson_4.jpg"></a>
    <a href="/assets/pages/others/igson-ip-camera/camera-igson_3.jpg"><img src="/assets/pages/others/igson-ip-camera/camera-igson_3.jpg"></a>
    <a href="/assets/pages/others/igson-ip-camera/camera-igson_5.jpg"><img src="/assets/pages/others/igson-ip-camera/camera-igson_5.jpg"></a>
</figure>

It looks ok, but have cut RJ45 connector. I managed to crimp new connector

<figure class="half">
    <a href="/assets/pages/others/igson-ip-camera/igson-rj45.jpg"><img src="/assets/pages/others/igson-ip-camera/igson-rj45.jpg"></a>
</figure>

I searched a lot and unfortunately there is no datasheet for this camera on the internet.

After connecting to my computer, I set up a DHCP server with the range 192.168.1.0/24. I found that the camera uses the IP address 192.168.1.211. Someone set it to this IP because later in the admin panel, I found that the default address is 192.168.1.120.

I tried to log in to the admin panel, but I don't know the password. Standard passwords like admin/admin won't work. There was a simple pop-up from my browser that asked me for the username and password. Using Wireshark, I discovered that the camera uses what's called **[Digest access authentication](https://en.wikipedia.org/wiki/Digest_access_authentication)**

Luckily, someone wrote a nice Python script for brute-forcing digest HTTP authentication on GitHub:  **[Bruteforce HTTP Authentication](https://github.com/kh4sh3i/bruteforce-http-authentication)**

You can also download zipped repo here:<br>
[Download bruteforce repo](/assets/pages/others/igson-ip-camera/bruteforce-http-authentication-main.zip){: .btn .btn--primary .btn--small}

To run this script, you need a brute-force dictionary. I found one on a GitHub repo: **[Bruteforce dictionary database](https://github.com/duyet/bruteforce-database)**

You can also download the zipped repo here:
[Download dictionary database repo](/assets/pages/others/igson-ip-camera/bruteforce-database-master.zip){: .btn .btn--primary .btn--small}

I used the 2151220-passwords.txt database and assumed that the user is 'admin'.

`python3 bruteforce-http-authentication.py -w http://192.168.1.211  -u admin -f 2151220-passwords.txt  -m digest`

Luckily, the brute-force attack succeeded, and I found the password:
<br>
`user: admin`
<br>
`password: 1111`




