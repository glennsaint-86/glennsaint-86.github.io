---
layout: single
title:  "Setting up new AWS Account"
date:   2022-10-15 01:20:25 +0800
categories: blog
toc: true
toc_sticky: true
tags: AWS cloud-provider aws-noob
#permalink:
published: true
---
This post is intended for newbie in Amazon Web Services and haven't setup/signup an account yet.  During signup, AWS starts with a 12-month free tier of popular services. For more information on the free acount, see [FAQ](https://aws.amazon.com/free/free-tier-faqs/) 

Below are the 3 basic requirements:
* Email account - to be use to type to your login
* Phone number - for verification process through SMS
* Credit card - for future billing purposes that are not covered in the free tier or your usage my go beyond the free tier limits. Make sure your credit card is not yet expired
* MFA Authentication software - can be installed on your mobile phone for 2FA

## Ceating an AWS Account

### Create account with email address
1. The first thing to do is create aws account 
2. Go to [AWS](https://aws.amazon.com/free)
3. Click on Create AWS account button, then you will be redirected to the signup page. Supply the following fields:
  
    1. Root Email Address which is your email account/address
    2. AWS account name

   <br/>See sample screenshot below for reference<br/>
    ![aws create account](/assets/images/aws-signup-02.png)

4. Click on the <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Verify email address</span> button, check your email for the verification code. Once received enter the verification code and click <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Verify</span> button. See sample screenshot below for reference<br/>
    ![aws verify email](/assets/images/aws-signup-03.png)

5. Nominate and enter your root password and click <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Continue</span> button<br/><br/>
    ![aws contact](/assets/images/aws-signup-04.png)

### Contact Information
Enter the necessary contact information such as address which includes city, state, zipcode and your primary mobile number. Once done click <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Continue</span> button. See sample screenshot below for reference

![aws contact](/assets/images/aws-signup-05.png)

### Billing Information
Enter your Credit Card information and your billing address. As for the billing address you can use your contact address enterd previously. Click on <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Verify and Continue</span> button. See sample screeenshot below for reference

![aws billing](/assets/images/aws-signup-06.png)

### Identity Confirmation
1. Based on the mobile number entered previously, AWS will call or send a verfication code. Click <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Send SMS</span> to continue. See sample screenshot below for reference

    ![aws ident confirmation](/assets/images/aws-signup-07.png)

2. Enter the SMS verification code sent

    ![aws ident confirmation](/assets/images/aws-signup-08.png)

### Select a support Plan
Choose Basic Support - Free, and click <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Complete sign up</span> button. See screenshot below for reference

![aws support plan](/assets/images/aws-signup-09.png)


### Setting up MFA to your AWS account for account protection
1. At this stage your AWS account has been created and behind the scenes it is preparing your account. A congratulations page will be displayed and click on <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Go to AWS Management console</span> button to continue.

    ![aws console](/assets/images/aws-signup-10.png)

2. Below is a sample screenshot on what email messages you will be receiving during the setup up to the completion process of your newly created account.

    ![aws email notifications](/assets/images/aws-signup-11.png)

3. Once you are in th AWS console management, on your profile at the upper right, click the dropdown menu and choose Security Credentials. Once the page has been loaded, look for the Assign MFA button and click it. See screenshot below for reference

    ![aws mfa setup](/assets/images/aws-signup-12.png)

4. Select an MFA device and click <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Next</span> button as illustrated in the screenshot below

    ![aws mfa device](/assets/images/aws-signup-13.png)

5. Setup your authenticator and click <span style="background-color:rgb(102, 102, 153);color:white;border:none;cursor:none;padding:2px 12px 3px 12px;text-decoration:none;">Add MFA</span> button once done. See screen below for reference

    ![aws assign mfa](/assets/images/aws-signup-14.png)

6. Viola, your MFA is complete setup. Seee screenshot below for reference 

    ![aws mfa done](/assets/images/aws-signup-15.png)

## Now what?
* Take time to read and understand [FAQ](https://aws.amazon.com/free/free-tier-faqs/) for the free offerings, this would help you know the limits and quotas so that you will not be charged in your credit card 
* When testing out AWS resources or doing some POC when done always delete/destory the resources to avoid additional charges
* To learn more on azure services and tutorials go to [aws skill builder](https://explore.skillbuilder.aws/learn)
