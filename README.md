![](./media/image1.jpeg)

*“An app to send SMS to keep you updated about your Freshdesk events”*

![](./media/image2.png)

Introduction
============

With Freshdesk, organization can set, manage, and meet customer expectations by providing consistent support service. The support team members can choose to get notified via email every time a ticket gets assigned to them. But as they gets lots of emails, it becomes a challenge to quickly identify critical emails and proactively respond and take prompt actions for critical customer queries.

For all urgent actionable items, email notification cannot be an effective medium, especially in case of providing helpdesk service. Any delay on the customer query impacts customer engagement and may result in a lost customer.

Over the past years, mobile has become the most impactful communication platform due to its massive adoption rate. And thus, Short Messaging Service (SMS) becomes an effective communication channel to deliver business-critical information in short timeframe to respective team members. SMS empowers support team members to stay on the top of the things that matter and allow them to proactively respond to customers.

Freshdesk with Nexmo SMS allows organization to facilitate proactive customer support service by enabling their support team to get notified through the SMS delivered for all the critical customer support tickets.

Use case
========

Configure Freshdesk to send SMS using Nexmo Messaging APIs for selected critical events. SMS should be delivered to the respective support team members for configured events.

Prerequisites 
==============

-   Admin credentials to configure Freshdesk platform.

-   Nexmo subscription and corresponding Nexmo API keys (Keys and Secret). To access the API keys, see appendix section.

-   Internet connectivity.

Features 
=========

-   Send SMS on any events supported by Freshdesk.

-   Make SMS dynamic by using Freshdesk placeholder.

Steps to use Nexmo configuration with Freshdesk
===============================================

1.  Login with admin credentials at <https://advaiya.freshdesk.com/helpdesk>

2.  From top menu, click on **Admin** option.

> ![](./media/image3.png)

1.  In the Helpdesk **Productivity Section,** click on **Observer** Icon.

    ![](./media/image4.png)

2.  Click on **New Rule** button.

    ![](./media/image5.png)

3.  Give appropriate name to your rule.

    ![](./media/image6.png)

4.  Select event from the drop down. In this example, we are creating rule for ticket update so select **Ticket is** from the first drop down and **updated** from the second drop down.![](./media/image7.png)

    You may select any event as per your need.

5.  Select **events performed by** as per your need.

    ![](./media/image8.png)

6.  You may configure further which tickets to be selected for this rule.

    ![](./media/image9.png)

7.  From **perform these actions,** under **Select Action,** select **Trigger Webhook.**

    ![](./media/image10.png)

8.  Select **Post** as your request type.

    ![](./media/image11.png)

9.  In **Callback URL** field put [**http://rest.nexmo.com/sms/xml**](http://rest.nexmo.com/sms/xml)

    ![](./media/image12.png)

10. Select **JSON** for encoding and **Advanced** for content field.

    ![](./media/image13.png)

11. You need to put your settings in following JSON format.

    **{**

    **"api\_key":"&lt;YOUR API KEY&gt;",**

    **"api\_secret":"&lt;YOUR API SECRET&gt;",**

    **"to":"&lt;NUMBER WHERE MESSAGE IS TO BE SENT&gt;",**

    **"from":"&lt;YOUR NEXMO FROM NUMBER&gt;",**

    **"text":"&lt;MESSAGE TEXT&gt; "**

    **}**

    You can use placeholder to make your settings dynamic. For example, if you want to send message to the ticket requester, Put cursor on **&lt;NUMBER WHERE MESSAGE IS TO BE SENT&gt;** place and click on **Insert Placeholder.**

    ![](./media/image14.png)

12. In **Requester** tab, select **Requester phone number**.

    ![](./media/image15.png)

13. Similarly, you can select any ticket property’s placeholder from **Tickets** tab for your message text. The final settings will look like as shown below:

    ![](./media/image16.png)

14. Click on **Save** button in the bottom.

15. You are done. Now you should receive SMS when any update is made on the tickets.

<span id="_Toc432770622" class="anchor"><span id="_Toc438631010" class="anchor"></span></span>Appendix
======================================================================================================

<span id="_Toc432770623" class="anchor"><span id="_Toc438631011" class="anchor"></span></span>Nexmo API Keys
------------------------------------------------------------------------------------------------------------

-   To access the Nexmo keys, go to <https://www.nexmo.com/> and sign-in.

-   In the top right corner, click on **Api Settings**.

-   Key and Secret will display in the top bar as shown in the below image:

> ![](./media/image17.png)