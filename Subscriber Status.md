# Subscriber Status

Subscriber Status in Salesforce Marketing Cloud (SFMC) is a critical concept that defines the current state or condition of a subscriber or contact within your marketing database. It plays a crucial role in email marketing and communication, helping you understand and manage your subscribers' engagement and preferences. Here's a breakdown of Subscriber Status, how it differs from Consent Status, possible values, and how it can change based on interaction events


## Possible Value

__1.Active__	

A subscriber who meets either of these criteria has a status of Active: No activities have occurred to make the subscriber's status Bounced, Undeliverable, Unsubscribed, or Deleted.
A subscriber whose status was Bounced or Undeliverable is recorded as having opened or clicked through a received email. In this case, the system changes the subscriber's status back to Active.

	
__2. Bounced (Returned)__

A subscriber who meets these criteria has a status of Bounced: one or more bounces, soft, or hard, are received for the subscriber

__3.Held (Undeliverable)__	
A subscriber who meets these criteria has a status of Held (Undeliverable): Three or more bounces, soft or hard, are received for the subscriber and more than 15 days have passed since the first bounce. If the bounce was from a trusted domain, only one hard bounce is required. To obtain a list of trusted domains, contact Salesforce Support. The status is reset to Active when a subscriber engages with the email.

__4. Unsubscribed__
A subscriber who meets any of these criteria has a status of Unsubscribed:

The subscriber has requested to be removed from a single list, multiple lists, or all lists. In these cases, the subscriber's status is changed to Unsubscribed for the selected lists or at the All Subscribers level. A user manually unsubscribes a subscriber, thus changing the status to Unsubscribed for the list at which the action was taken. The subscriber has submitted a spam complaint in the user interface of any ISP or webmail service that provides a feedback loop (FBL) to ET. In this case, the subscriber's status is changed to Unsubscribed at the All Subscribers level. When the Sender Authentication Package is applied, ISPs that offer feedback loops include:
- AOL
- Hotmail
- Comcast
- Roadrunner
- Synacor
- Cox Cable
- Excite/BlueTie
- Mailtrust
- IBM/Outblaze
- Tucows/OpenSRS
- Juno
- USA.net
- Yahoo
- Others can also be included.

__5. A subscriber who meets either of these criteria has a status of Deleted:__

A user has deleted a subscriber from a list other than the All Subscribers list. In this case, the subscriber's status for that list only is Deleted. A user has deleted a subscriber from the All Subscribers list. In this case, the subscriber's global status is Deleted.

__Subscriber Status will change according to diagram below__

![alt text](https://github.com/WPNCH/SFMC/blob/main/Images/SFMC%20substatus.jpg)

# How Subscriber Status Work in Parent and Child Business Unit

In Salesforce Marketing Cloud (SFMC), Subscriber Status can function differently when you have a Parent Business Unit and Child Business Units. To understand this, let's explore how Subscriber Status works in both scenarios and how it is linked to the BusinessUnitUnsubscribes DataView and _List DataView:

__1. Parent Business Unit:__

In a Parent Business Unit, Subscriber Status is typically managed at the Parent level and applies to all subscribers across all Child Business Units. This means that if a subscriber unsubscribes or changes their status in the Parent Business Unit, it will impact their status and subscription preferences across all Child Business Units. The BusinessUnitUnsubscribes DataView at the Parent level contains information about unsubscribed subscribers and their status changes across all Business Units within the Parent. The _List DataView at the Parent level stores lists of subscribers, and you can manage Subscriber Status for these lists in a centralized manner, affecting all Child Business Units.

__2. Child Business Units:__

In Child Business Units, Subscriber Status can be inherited from the Parent Business Unit, but it can also be managed independently. This allows Child Business Units to have some autonomy in controlling their subscribers' statuses and preferences. When Subscriber Status is managed independently in a Child Business Unit, it only affects subscribers within that specific Child Business Unit, and changes won't impact subscribers in other Child Business Units or the Parent Business Unit. The BusinessUnitUnsubscribes DataView at the Child Business Unit level stores data related to unsubscribed subscribers specific to that Child Business Unit. Changes here will not affect subscribers in other Child Business Units or the Parent.

__3. Link to BusinessUnitUnsubscribes DataView:__

The BusinessUnitUnsubscribes DataView is essential for tracking unsubscribed subscribers and their status changes within a specific Business Unit (either Parent or Child). It provides details on when subscribers unsubscribed, the reason for unsubscribing, and their current status within that Business Unit. This DataView is a valuable resource for compliance and auditing purposes, allowing you to keep track of subscriber preferences and ensure that you're not sending emails to those who have opted out.

__4. Link to__ ___List DataView:__

The _List DataView is used to manage lists of subscribers within a Business Unit. Lists can be created for specific marketing campaigns or purposes. Subscriber Status can be managed within lists, allowing you to control who receives emails for a particular campaign. The _ListSubscriber DataView can provide insights into the subscribers within these lists, including their current status and other attributes.
