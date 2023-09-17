# PRTG SMS Gateway(Grep Tech)

This is a documentation on how to configure Greptech Smsgateway with PRTG.
There are 2 methods to use PRTG to delievery SMS notiifcation. 

# Method 1 - HTTP API

Using Greptech http api in PRTG provides a straightforward sms notification.This method is a clear demarcation between PRTG AND sms notifications.In short what is not monitored via PRTG, no sms notification would be sent.

Setting SMS deleivery for PRTG via API for GREP TECH SMS gateway

1) on PRTG -> https://127.0.0.1/systemsetup.htm?tabid=3

2) go to setup -> under sms delivery -> Custom URL(enter API) -> http://smsgateway_IP/api.php?md=send_sms&user=admin&pass=Notify&num=%SMSNUMBER&msg=%SMSTEXT

Pro of using this method 

All messages constant with PRTG. As the sms genrated is the actual fault/Warning capture by PRTG. PRTG send directly the device fault/Warning via SMS.

Con of using this method

No all fault can be captured Only devices configure on PRTG is captured.

![alt text](https://github.com/ioctlsg/PRTG_SMS_Gateway/blob/main/Image%2011-8-23%20at%205.07%20PM.jpg)

# Method 2 - SMTP Trap

This method primarily uses SMTP trap on the device being monitored. An additional feature on the smsgateway need to be purchase. For GrepTech smsgateway a trap2sms plugin is required.
GrepTech Smsgateway monitors all smtp traps send to it, upon receiving a sms trap, the Smsgateway would do a matching of the OID, when a OID matches the "configured OID" a sms notification would be sent.

in short, the Smsgateway has no dependencies as long as it receives a smtp trap and matches in its configuration file it would send a sms.
Therefore smtp devices can directly send smtp traps to the Smsgateway without the need of PRTG.

this may or may not complicate the over monitoring design.
In this case PRTG send a SMTP trap to sms gateway when a Fault/Warning occurs. 

Pro of using this method

SMS Traps that isn't configured on PRTG can be send directly to SMS gateway.

Con of using this method

Only PRTG OID is sent to SMS gateway. PRTG appends the additional information to PRTG but doesn't give a better picture of which device actually is sending the trap.

![alt text](https://github.com/ioctlsg/PRTG_SMS_Gateway/blob/main/Image%2011-8-23%20at%204.58%20PM.jpg)



References

https://www.grep.sg/http-sms-api/

https://blog.paessler.com/sending-prtg-sms-notifications
