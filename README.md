# PRTG_SMS_Gateway

There are 2 methods to use PRTG to delievery SMS notiifcation. Below would walk over the 2 methods

# Method 1 - HTTP API

Setting SMS deleivery for PRTG via API for GREP TECH SMS gateway

1) on PRTG -> https://127.0.0.1/systemsetup.htm?tabid=3

2) go to setup -> under sms delivery -> Custom URL(enter API) -> http://192.168.10.11/api.php?md=send_sms&user=admin&pass=Notify&num=%SMSNUMBER&msg=%SMSTEXT

Pro of using this method 

All messages constant with PRTG. As the sms genrated is the actual fault/Warning capture by PRTG. 

Con of using this method

No all fault can be captured Only devices configure on PRTG is captured.


# Method 2 - SMTP Trap

This method



References

https://www.grep.sg/http-sms-api/
