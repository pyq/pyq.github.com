---
layout: post
title: "Launch Instance of EC2 AWS"
description: "AWS EC2"
category: "cloud computing"
tags: [Cloud Computing]
---
{% include JB/setup %}
#SSH into the instance of EC2

Open your command shell and run the following command:
>$ ssh -i /path/key_pair.pem ec2-user@public_dns_name

but here we might get a warning that is the private key is too open.  
execute the following command, substituting the path for your private key file.
>$ chmod 0400 path/my_private_key.pem


For the mindterm still have problem.