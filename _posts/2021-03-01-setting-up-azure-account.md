---
layout: single
title:  "Setting up new Azure Account"
date:   2021-03-01 00:00:25 +0800
categories: blog
toc: true
toc_sticky: true
tags: Azure cloud-provider azure-noob
#permalink:
published: true
---
This post is intended for newbie in Microsoft Azure and haven't setup/signup an account yet.  During signup, Microsoft Azure offers $200 credit valid for 30 days, 12 months of free popular services and 25+ services that are always free. For more details on the free account, see [FAQ](https://azure.microsoft.com/en-gb/free/free-account-faq/).

Below are the 3 basic requirements:
* Microsoft account - goto [Microsoft Account](https://account.microsoft.com) to create a new account
* Phone number - for verification process through SMS
* Credit card - for future billing after you've consume the $200 credit or after 30 days. 


## Ceating an Azure Account

1. The first thing to do is create a Microsoft account 
2. Go to [Microsoft Azure](https://azure.microsoft.com/en-gb/free)
3. Click on Start Free button
4. Use the Microsoft Account created in step #1
5. Enter your Profile details, see sample screenshot below
    ![azure signup profile](/assets/images/azure-signup-01.png)
6. Click on Next button, for phone and credit card verfication
7. Once the the phone number and credit card will be verified, you will be redirected to a page that will have a content
   
   # You're ready to start with Azure, {emailaddress}!
   where `{emailaddress}` is you're microsoft account.

## Logging in to Azure Portal

1. Go to [Azure Portal](https://portal.azure.com) and login using you're Azure account
2. Since the account created is free, you would notice a word **Upgrade** in the topmost bar as illustrated below
   ![azure free account indicator 1](/assets/images/azure-free-indicator-01.png)
   
   During the initial signup, there is also a notification indicating that you have $200 credits that is valid in 30 days as illustrated below
   ![azure free account indicator 2](/assets/images/azure-free-indicator-02.png)
3. In the top bar, there is a search field in the middle. Type-in `Subscriptions` and hit ENTER to go to Azure Subscriptions. It will show one subscription named `Azure Subscription 1`, click on it to go to the details of the subscription. Under overview, scroll down to see quotas/limits of the free servies for 12 months. Below is a sample illustration
   ![azure free subscription](/assets/images/azure-subs-01-compress.gif)

## Now what?

* Azure offers a "Try it free" for 30 days with $200 credits to explore azure services and learn
* Take time to read and understand [FAQ](https://azure.microsoft.com/en-gb/free/free-account-faq/) for the free offerings, this would help you know the limits and quotas so that you will not be charged in your credit card 
* When testing out azure resources or doing some POC when done always delete the resources to avoid additional charges
* To learn more on azure services and tutorials go to [Microsoft Learn](https://learn.microsoft.com)
