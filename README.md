# Registration-Procedure

When a 5G device his first turn on, it needs to register itself with the network before it can access the 5G services. This process is known as registration. But power on is not only the situation when this registration happens. It can be defined in four categories such as 

i) initial procedure <br />
ii) periodic procedure <br />
iii) mobility procedure <br />
iv) emergency procedure <br />

First, power-on procedure is known as initial procedure. In addition it also have periodic registration, this is to make sure that the device has not run out of battery or has been broken. So, the device was doing periodic registration if it is inactive somehow. Mobility registration, in which the device has to register itself if it is moving to a new location. Emergency registration, which is service registration situation where the device which is like to access the emergency services like emergency call needs to register itself.

**Registration Procedure Call Flows**

First step in the registration procedure is the registration request. For example, when the device is turned-on, the device sends a registration request to RAN. Now the RAN has to forward that to the core network to the appropriate AMF. But how would RAN knows what is the appropriate AMF. Here there are two possibilities.

In first scenario, if the device has already been communicating with 5G network, then it will have an identity assigned (GUTI). There is a temporary identifier as indication exactly which AMF the device has previously registered with. So using this to know which AMF, the device was previously communicating and through which RAN can forward the request to the corresponding AMF. 
