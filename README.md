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

Second if there is no previous identity is available it means this is the first power on procedure. So the RAN looks at registration request and the registration request as slice identifier (NSSAI). Then based on this slice identifier for this particular network slice they can see, which AMF supports network slice and forward the registration request to this corresponding AMF. 

Once that registration request is forwarded AMF. We have context transfer as a next step. Let us assume the registration request is because of mobility. So the device is moved to a new region and trying to do a registration update and as the result it is trying to connect to the new AMF. But because this is the mobility triggered process, the device already has the UE context established with the old AMF. So in such situation, in Step 2 where the AMF contact with the old AMF for transferring the UE context and then the old AMF respond by communicating and transmitting the UE context to the new AMF. 

Now the step 3 is authentication, which carried out using the 5G authentication and key agreement procedures. So the third step is related to authentication and security. 

Step 4, previously no AMF has taken over the UEContext. In this step the new AMF has confirmed with old AMF that it has taken over the UE context. And that AMF responsible for accessing and mobility from now.

In Step 5, the new AMF will register itself with the UDM, saying that I am the new AMF, so take care of my valid information. And then it speaks to the UDM to get the necessary subscription information and it will also subscribe for any further updates to the subscription information in the future. Because the new AMF controls the access and mobility, so it needs to know what is the subscription status of the device that doing the registration. On the other hand when a new AMF is taking over, the old AMF has to retire. For this purpose, the UDM will notify the old AMF that needs to deregister. So the old AMF, will now unsubscribe to any subscription data that it has previously subscribed to. So the transfer to new AMF has complete and the old AMF has successfully retired according to the UDM database.

In step 6, AMF needs to know the necessary policies related to access and mobility management. So it goes to PCF and fetches the necessary policy information corresponding to that particular device that is undergoing registration and the PCF provide the corresponding response. 

In step 7, if there is already an existing PDU session, then the AMF speaks to the SMF to continue the PDU session using the update as some context message. On the other hand, if there is some kind of mismatch in understanding of what PDU session state is, then previous PDU session is terminated using the release session management context message and then a new PDU session is created if necessary. 

In step 8, if registration procedure so far has gone good then the AMF will notify the device that the registration has been accepted and optionally, the device can send the confirmation saying that I have received the registration acceptance and registration complete message will be sent from device to the AMF. 

In step 9, the AMF will contact with PCF for any device specific policies. Since there are some policies that help the device decisions. For example, the device might have to decide for a specific application if it has to create a new PDU session and or not. If there are multiple Wi-Fi networks that are supported, which one should be the device prioritize to use in support with the 5G network. This kind of policies can now be fetched from PCF.
