#Charter for Working Group

There are many situations in which it is desirable to share a digital credential with another person. For example, you may want to provide access to your vehicle to a friend or a family member. You may also want to provide access to your home to your cat sitter. Or, you may want to share a hotel key with your spouse. Today, no such standardized method exists in a cross-platform, multidisciplinary capacity. 

The WG charter includes the definition and standardization of a protocol that will facilitate such credential transfers from individual to individual. The protocol will leverage a “relay server” to transfer data from sender to recipient. The scope of the transfer is limited to a single origin device and a single destination device. Note that neither private keys nor secret symmetric keys present on the sender's device are exchanged during the transfer operation. In the transfer protocol, the "credential" being sent from sender to recipient comprises data both necessary and sufficient for the recipient to exchange with the credential authority for new digital key material granting the recipient a subset of the sender's capabilities or entitlements.

Privacy goals include:

- The relay server should not see sensitive details of the share
- The relay server should not be able to provision the credential itself, acting as an intermediary for the recipient (man-in-the-middle, impersonation attack)
- Aside from potentially the IP address, the relay server should not learn the identity of the sender or receiver 

Sufficient security measures should be embedded in the protocol in an effort to:

- Ensure only the intended recipient is able to provision the credential
- Ensure the credential can only be provisioned once (anti-replay)
- Ensure the sender has intent to share (secure user intent, proof of the fact that the share initiation is attributed to a valid device and a user)

The solution the WG comes up with must:

- Allow a sender to initiate a share and define a relay server
- Allow a recipient to view the share request, and provision the credential associated with the share upon receipt
- Allow dynamic message formats based on the credential type (the protocol should be able capable of carrying various types of credentials)
- Allow sender device and receiver device to quickly perform multiple round trip communications

Out of scope topics for the WG are:

- Defining the mechanism the receiver will use in order to provision the credential
- The WG will define the full set of different credential types that could be shared. A subset of these credential types adhere to a public standard. For these credential types, the format of the Provisioning Information shall be defined by the appropriate standard. Other credential types may be proprietary. For these credential types, the protocol the WG aims to establish shall not define the actual format nor content of each field within the Provisioning Information.
- The User Interface (UI) that is displayed to the sender or receiver during sending or receiving - this will depend on the device OEM’s UI and HI guidelines.

The WG will deliver a protocol to facilitate secure credential transfer. The WG must consider all Privacy and Security considerations in an effort to perform the credential transfer in a secure manner. The protocol will use appropriate cryptographic mechanisms to protect the transferred credentials in accordance with the security and privacy goals described above.
