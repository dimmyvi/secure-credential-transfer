# TIGRESS Charter ("Transfer dIGital cREdentialS Securely")

There are many situations in which it is desirable to transfer a copy of a digital credential to another person. For example, a person may want to provide access to their vehicle to a friend or a family member. A person may also want to provide access to their home to a cat sitter. Or, a person may want to transfer a copy of a hotel key to their partner. Today, no such standardized method exists in a cross-platform, credential type-agnostic capacity. 

The WG charter includes the definition and standardization of a protocol that will facilitate such credential transfers from one person's device to another person's device. The protocol will leverage a “relay server” to transfer data from sender to recipient. The scope of the transfer is limited to a single sending device and a single receiving device. The data exchanged comes from a credential authority, which can vary from a car owner to a hotel company depending on the use case. Note: neither private keys nor secret symmetric keys present on the sender's device are exchanged during the transfer operation. In the transfer protocol, the "credential" being transferred from sender to recipient comprises data both necessary and sufficient for the recipient to exchange with the credential authority for new digital key material granting the recipient a subset of the sender's capabilities or entitlements. Therefore, the sender is actually authorizing the recipient to provision a digital credential from the credential authority with certain access rights.

Privacy goals include:

- The relay server should not see sensitive details of the share (e.g. personaly identifiable information, cryptographic keys, etc)
- The relay server should not be able to provision the credential itself, acting as an intermediary for the recipient (person-in-the-middle, impersonation attack)
- Aside from potentially the IP address, the relay server should not learn the identity of the sender or receiver 

Sufficient security measures should be embedded in the protocol in an effort to:

- Ensure only the intended recipient is able to provision the credential
- Ensure the sender has intent to share (proof of the fact that the share initiation is attributed to a valid device and a user)

The solution the WG comes up with must:

- Allow a sender to initiate a share and select a relay server
- Allow a recipient to view the share request, and provision the credential associated with the share upon receipt
- Allow a sender and a recipient to perform multiple round trip communications within a limited time frame
- Support opaque message content based on the credential type
- Support a variety of types of credentials, to include those adhering to public standards (e.g., Car Connectivity Consortium) and proprietary (i.e., non-public or closed community) formats

The following topics are out of scope for the WG:

- Defining the mechanism the receiver will use in order to provision the credential with the credential authority
- The User Interface (UI) that is displayed to the sender or receiver during sending or receiving (this will depend on the device manufacturer's interface guidelines) 
- Defining the format or content of each field within the encrypted data (i.e., the provisioned credentials and associated information) stored on the relay server
- Ensuring the solution does not allow for inappropriate data or "cat pictures" to be stored

The WG will deliver a protocol to facilitate secure credential transfer. The WG must consider all Privacy and Security considerations in an effort to perform the credential transfer in a secure manner. The protocol will use appropriate cryptographic mechanisms to protect the transferred credentials in accordance with the security and privacy goals described above. More information for the requirements and use cases for this working group can be found in our Requriements document (https://datatracker.ietf.org/doc/draft-tigress-requirements/). 

Planned Deliverables:

2022-09: WG adoption of Requirements document
2022-12: WG adoption of the secure credential transfer protocol
2023-12: Submit secure credential transfer protocol to the IESG for publication
