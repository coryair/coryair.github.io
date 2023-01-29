---
title:  "Monitoring error logs within AWS Organizations"
date:   2023-01-28 15:46:50 -0700
categories: aws organizations eventbridge event-driven
---
A lot of tickets that come via AskAlteryx are access denied or unauthorized messages. 

For example, creating a role without our Permissions Boundary, you get an error. Or Creating a default VPC. It would be nice if AWS would say, "hey you can't do this because of this reason", but you get a weird message instead. 
