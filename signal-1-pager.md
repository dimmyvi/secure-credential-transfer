# Signal Protocol 1 pager

The Signal Protocol is a secure messaging protocol that provides end-to-end encryption for instant messaging and voice/video calls. The Signal Protocol is primarily used through the Signal app, which is available for both Android and iOS devices. However, there are some alternative implementations of the Signal Protocol that allow developers to use it without the Signal app. For both Android and iOS, the Signal app provides and API that allows developers to integrate with the Signal Protocol into their own applications. For this document, we will focus on this implementation of the Signal Protocol. 

## Secure Credential Transfer with Signal Protocol:

For Secure Credential Transfer with Signal Protocol, the message sequence and message contents will be the same as the other approaches. However, instead of hosting an intermediary server (WebDAV or other), the credential application will have to implement the Signal app API to establish a secure connection between sender and receiver. 

Once this secure connection is established, the credential application on the sender’s device will send the provisioning information to the receiver’s signal account. The destination credential application will also have to implement this API in order to receive this information. For stateless sharing, the destination credential application will take that provisioning information and provision the credential. 

For the stateful sharing flow, the receiving credential application will send data to the sender’s device and the sender will send a final package back to the receiver. Since the credential applications are directly communicating with the Signal app to establish connectivity, the receiving user would potentially have no action required to complete the provisioning. 

While this is guaranteed to be a secure method of transferring data between users, there are a few considerations. In this use case, both sender and receiver have to have accounts with Signal App to complete the communication. Signal App is currently available on iOS and Android, so most users are able to make accounts for free. However, it may limit sharing for sender and receiver pairs that only have one method of contact outside of Signal. It is worth noting that while the Signal Protocol is open source, the Signal Protocol libraries for iOS and Android are not. The libraries are licensed under the GPLv3 license, which allows for use and modification, but they also include some proprietary components that are not open source.
