---
title: "NETCONF Transport Port Numbers"
abbrev: "NETCONF Transport Port Numbers"
category: std

docname: draft-ietf-netconf-port-numbers-latest
submissiontype: IETF
number:
date:
consensus: true
v: 3
area: "Operations and Management"
workgroup: "Network Configuration"
keyword:
 - de-assign
 - deallocate
 - release


author:
 -
    fullname: Mohamed Boucadair
    organization: Orange
    email: mohamed.boucadair@orange.com

normative:

informative:
  IANA-SERVICE:
     title: Service Name and Transport Protocol Port Number Registry
     target: https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml

--- abstract

This document releases NETCONF-related port number IANA assignments that have not stood the test of time
(e.g., assignments for Historic NETCONF-related protocols).

--- middle

# Introduction

The "Service Name and Transport Protocol Port Number" registry
{{IANA-SERVICE}} records several NETCONF-related port and service name assignments
such as 830 for NETCONF over Secure Shell (SSH) {{?RFC6242}}, 831 for NETCONF over the Blocks Extensible Exchange Protocol (BEEP) {{?RFC4744}},
832 for NETCONF over the Simple Object Access Protocol (SOAP) {{?RFC4743}}, 4334 for NETCONF Call Home {{?RFC8071}},
and 6513 for NETCONF over Transport Layer Security (TLS) {{?RFC7589}}{{?I-D.ietf-netconf-over-tls13}}.

However, many of these assignments are for a transport protocol (i.e., UDP) for which
the requesting application does not apply. Also, many of the assignments are for protocols that are not deployed and were tagged as Historic: {{?RFC4743}} and {{?RFC4744}}.

This document de-assigns these unused port numbers.

Consistent with {{Section 8.2 of !RFC6335}}, this document does not de-assign service names; only port numbers are de-assigned for better usage of available scarce resources.

Releasing back some port numbers softens the exhaustion risk of available port number space (especially the System
Ports range ({{Section 6 of !RFC6335}})).

# Operational Considerations

There are no known implementations and deployments of protocols that rely upon the port numbers released back by this document. As such, there are no new operations or manageability requirements introduced by this document.

# Security Considerations

This document does not describe any protocol. As such, this document does not introduce any new security vulnerability.

# IANA Considerations

This document requests IANA to update the "Service Name and Transport Protocol Port Number Registry"
registry {{IANA-SERVICE}} as specified in the following subsections.

> Note to the RFC Editor: Please replace "THIS_DOCUMENT" with the RFC number to be assigned to this document.

## NETCONF over SSH Service

OLD:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconf-ssh  |830|	tcp|	NETCONF over SSH|	{{?RFC6242}} |
|netconf-ssh|830|udp|	NETCONF over SSH	|{{?RFC6242}} |

NEW:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconf-ssh  |830|	tcp|	NETCONF over SSH|	{{?RFC6242}} |

A note can be added to 830/udp to indicate that the port number used to be assigned to NETCONF over SSH but released by THIS_DOCUMENT.

## NETCONF over BEEP Service

OLD:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconf-beep|831|tcp|	NETCONF over BEEP	| {{?RFC4744}} |
|netconf-beep|831|udp|	NETCONF over BEEP|	{{?RFC4744}} |

NEW:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconf-beep|||	NETCONF over BEEP	| {{?RFC4744}} THIS_DOCUMENT |

A note can be added to 831 to indicate that the port number used to be assigned to NETCONF over BEEP but released by THIS_DOCUMENT.

## NETCONF over SOAP Service

OLD:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconfsoaphttp	|832|tcp|	NETCONF for SOAP over HTTPS|	{{?RFC4743}} |
|netconfsoaphttp	|832|udp|	NETCONF for SOAP over HTTPS|	{{?RFC4743}} |
|netconfsoapbeep	|833|tcp|	NETCONF for SOAP over BEEP|	{{?RFC4743}} |
|netconfsoapbeep|	833|udp|	NETCONF for SOAP over BEEP	| {{?RFC4743}} |

NEW:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconfsoaphttp	| | |	NETCONF for SOAP over HTTPS|	{{?RFC4743}} THIS_DOCUMENT |
|netconfsoapbeep	| | |	NETCONF for SOAP over BEEP |	{{?RFC4743}} THIS_DOCUMENT |

A note can be added to 832/833 to indicate that the port numbers used to be assigned to NETCONF over SOAP but released by THIS_DOCUMENT.


--- back

# Acknowledgments
{:numbered="false"}

Thanks to Amanda Baber and Zahed Sarker for the guidance. Thanks to Tom Petch for the comments.

Thanks to Kent Watsen for the Shepherd review, Mahesh Jethanandani for the AD review,
Bernie Volz for the intdir review, Roni Even for genart review, and Barry Leiba for artart review.
