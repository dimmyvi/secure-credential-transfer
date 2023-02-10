# WebDAV 1 pager

WebDAV (Web Distributed Authoring and Versioning) is a protocol that allows users to edit and manage files on remote web servers. It extends the HTTP protocol, adding functionality for creating, editing, and moving files and directories on a remote server. The protocol is defined in RFC 4918, "HTTP Extensions for Web Distributed Authoring and Versioning (WebDAV)". Since the core of transferring secure credentials is to allow a data blob to pass between two users, we can leverage the WebDAV protocol to create the secure communication channel between sender and receiver.

## Secure Credential Transfer with WebDAV:

For Secure Credential Transfer with WebDAV, the implementing party will host a remote WebDAV server that mobile devices can interact with. This will act as an intermediary between the sender and receiver device to create a safe communication channel. 

There are two different workflows for transferring of digital credentials. Refer to Credential Transfer Workflows in Secure Credential Transfer Draft: https://github.com/dimmyvi/secure-credential-transfer/blob/main/draft-secure-credential-transfer.md#credential-transfer-workflows. For the stateless flow, the sender device will upload a file with the provisioning information required for the receiver to redeem the pass using HTTP PUT. Because this is the final state this resource will be in, the sender will also perform a HTTP LOCK on the resource. 

The sender will then send the link to the remote server with the resource to the receiving device over any communication channel available to them. The URI for the resource will follow this format: “https://{RelayServerHost}/v{ApiVersion}/{ShareIdentifier}/share.json”. The WebDAV server implementor shall choose the ShareIdentifier for each resource to ensure there are no duplicates. 

Once the receiver has the link, they are able to access the resource with HTTP GET. Optionally, the implementor can incorporate OpenGraph metadata into the response of the GET request so users have a preview of what they are accepting. At this point, the receiver device can optionally call HTTP DELETE to remove the resource from the WebDAV server.

For the stateful use case, there is a requirement for multiple round trips between devices. In this case, both the sender and receiver will be reading resources with HTTP GET and putting a new or modified resource onto the WebDAV server with HTTP PUT. Once the receiver has redeemed, they can optionally call HTTP DELETE. 

In either case, the WebDAV remote server should clean up any remaining resources after a short period, such as 24 hours for example. 

Continue to use the same structure as defined here: https://github.com/dimmyvi/secure-credential-transfer/blob/main/draft-secure-credential-transfer.md#provisioning-information-structure. Both users must implement WebDAV in order to share and receive keys. As noted in the other solutions, WebDAV will only be used to share the data that is necessary and sufficient to redeem the key. Once the data is obtained by the receiver, it is up to the device OEM or other implementor to redeem that key with the credential authority. 
