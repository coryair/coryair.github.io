---
layout: post
title: Capturing AWS Organization Events with EventBridge and Buses and Taking Action
date: 2025-01-01 12:00:00
description: Learn how to reduce support tickets and automate responses by capturing AWS Organization events with EventBridge and event buses. Step-by-step guide for implementing cross-account event tracking and automated remediation using CloudTrail logs.
tags: AWS Events
categories: Observability Platform Events
---

Happy New Year!

--

I wanted to capture select events across my AWS Organization. We had 250+ accounts doing various things, and with new accounts being created daily, our ticket queue was growing fast. Most questions were about error messages from Service Control Policies (SCPs) or permission errors from users' permission sets.

These messages are logged by default in CloudTrail. EventBridge lets you capture specific events or a wide range of them. Once you decide what events to track, you can send them to an event bus, which can forward them to another event bus in another account. From there, you can take action on events that hit that bus.

## Before Event Tracking

A user tries to perform an action prohibited by our policies. They get a generic "access denied" error message with confusing details they can't decipher. This usually leads to a support request.

## After Event Tracking

A user tries to perform a prohibited action. They still get the same confusing error, but then receive an email or Slack message:

"Hello Jack,

You recently tried to perform X but got an access denied error. This is due to company policy. Here's how to do what you need: [Link to internal documentation]

Thanks,
Cloud Team"

You can see how this cuts down support requests and saves everyone time.

## Taking it Further

Emails aren't the only possible action. You can create custom Lambdas to perform actions within AWS itself.

Example: A user creates an EC2 instance in a VPC with public access (Internet Gateway, NAT Gateway, etc.) and sets up a security group allowing ALL TRAFFIC. We can detect this and automatically remediate it, then email the user about our actions to prevent confusion.

Since CloudTrail captures almost everything, you can implement whatever use case you imagine. As a Cloud Engineer, this has saved my team significant time, letting us focus on value-adding work.
