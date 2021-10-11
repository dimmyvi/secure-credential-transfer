---
title: "Secure Credential Transfer"
abbrev: "Secure Credential Transfer"
docname: draft-securecredential-transfer-latest
category: std

ipr: trust200902
area: TODO
workgroup: TODO Working Group
keyword: Internet-Draft

stand_alone: yes
smart_quotes: no
pi: [toc, sortrefs, symrefs]

author:
 -
    name: Dmitry Vinokurov
    organization: Apple Inc
    email: dvinokurov@apple.com
 -
    name: Matt Byington
    organization: Apple Inc
    email: 
 -
    name: Casey Astiz
    organization: Apple Inc
    email: 
 -
    name: B. Chester
    organization: Apple Inc
    email: 
 -
    name: A. Pelletier
    organization: Apple Inc
    email: 
 -
    name: Matthias Lerch
    organization: Apple Inc
    email: 

normative:

informative:


--- abstract

This document describes a mechanism to transfer digital credentials securely between two devices
Secure credentials may represent a digital key to a hotel room, a digital key to a door lock in a house 
or a digital key to a car. Devices that share credentials may belong to the same or two different platforms (e.g. iOS and Android).
Secure transfer may include one or more write and read operations.
Credentials transfer needs to be performed securely due to the sensitive nature of the information.

--- middle

# Introduction

Today, there is no standard way of transferring digital credentials securely between two devices 
belonging to the same platform or two different platforms. This document proposes a solution to this problem 
by introducing a Relay server which allows devices to exchange encrypted Provisioning Information securely.
The Relay server solves this problem by creating and managing temporary mailbox storage.

Each mailbox can be referenced by devices from a unique mailbox identifier in a URL.
The URL pointing to encrypted Provisioning Information is to be passed between devices directly 
over various channels (e.g. SMS, email, messaging applications).
The exchange of the URL is outside of the scope of this document.

This document describes a Hypertext (HTTP) Application Programming Interface (API) that allows 
Sender and Receiver devices to interact with a Relay server in order to perform secure credential transfer.


# Terminology

{::boilerplate bcp14-tagged}


# Security Considerations

This section discusses security considerations for the protocol.


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments

TODO acknowledge.
