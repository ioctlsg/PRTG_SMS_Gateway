# PRTG_SMS_Gateway

There are 2 methods to use PRTG to delievery SMS notiifcation. Below would walk over the 2 methods

# Method 1 - HTTP API

Setting SMS deleivery for PRTG via API for GREP TECH SMS gateway

1) on PRTG -> https://127.0.0.1/systemsetup.htm?tabid=3

2) go to setup -> under sms delivery -> Custom URL(enter API) -> http://192.168.10.11/api.php?md=send_sms&user=admin&pass=Notify&num=%SMSNUMBER&msg=%SMSTEXT

Pro of using this method 

All messages constant with PRTG. As the sms genrated is the actual fault/Warning capture by PRTG. PRTG send directly the device fault/Warning via SMS.

Con of using this method

No all fault can be captured Only devices configure on PRTG is captured.

![alt text](https://github.com/ioctlsg/PRTG_SMS_Gateway/blob/main/Image%2011-8-23%20at%205.07%20PM.jpg)

# Method 2 - SMTP Trap

This method primarily uses SMTP trap on the device being monitored. 

In the case PRTG genrates the SMTP trap to sms gateway when a Fault/Warning occurs. 

Pro of using this method

SMS Traps that isn't configured on PRTG can be send directly to SMS gateway.

Con of using this method

Only PRTG OID is sent to SMS gateway. PRTG appends the additional information to PRTG but doesn't give a better picture of which device actually is sending the trap.

![alt text](https://github.com/ioctlsg/PRTG_SMS_Gateway/blob/main/Image%2011-8-23%20at%204.58%20PM.jpg)



References

https://www.grep.sg/http-sms-api/

https://blog.paessler.com/sending-prtg-sms-notifications
