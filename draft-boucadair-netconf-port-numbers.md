---
title: "NETCONF Transport Port Numbers"
abbrev: "NETCONF Transport Port Numbers"
category: std

docname: draft-boucadair-netconf-port-numbers-latest
submissiontype: IETF
number:
date:
consensus: true
v: 3
area: "Operations and Management"
workgroup: "Network Configuration"
keyword:
 - de-assign


author:
 -
    fullname: Mohamed Boucadaor
    organization: Orange
    email: mohamed.boucadair@orange.com

normative:

informative:
  IANA-SERVICE:
     title: Service Name and Transport Protocol Port Number Registry
     target: https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml

--- abstract

This document releases NETCONF-related port number IANA assignments that were made
for inappropriate transport protocols or for an Historic NETCONF-related protocol.

--- middle

# Introduction

The following table lists currently (per 2024) assigned port numbers {{IANA-SERVICE}}
for various NETCONF transports.

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconf-ssh  |830|	tcp|	NETCONF over SSH|	{{?RFC6242}} |
|netconf-ssh|830|udp|	NETCONF over SSH	|{{?RFC6242}} |
|netconf-beep|831|tcp|	NETCONF over BEEP	| {{?RFC4744}} |
|netconf-beep|831|udp|	NETCONF over BEEP|	{{?RFC4744}} |
|netconfsoaphttp	|832|tcp|	NETCONF for SOAP over HTTPS|	{{?RFC4743}} |
|netconfsoaphttp	|832|udp|	NETCONF for SOAP over HTTPS|	{{?RFC4743}} |
|netconfsoapbeep	|833|tcp|	NETCONF for SOAP over BEEP|	{{?RFC4743}} |
|netconfsoapbeep|	833|udp|	NETCONF for SOAP over BEEP	| {{?RFC4743}} |
|netconf-ch-ssh|4334|tcp|	NETCONF Call Home (SSH) |	{{?RFC8071}} |
|netconf-ch-tls|4335|tcp|	NETCONF Call Home (TLS) |	{{?RFC8071}} |
|netconf-tls|6513|tcp|	NETCONF over TLS	| {{?RFC7589}}[RFC-ietf-netconf-over-tls13-04] |

Many of these assignments are for a transport protocol (UDP) for which
the requesting application does not apply. For example:

* "Using the NETCONF Protocol over "the Blocks Extensible Exchange Protocol (BEEP)"
specification ({{Section 7 of ?RFC4744}}) states the following:

{: quote}
>    IANA assigned TCP port (831) for NETCONF over BEEP.

* "Using the NETCONF Protocol over Secure Shell (SSH)" specification ({{Section 7 of ?RFC6242}}) states the following:

{: quote}
>    Based on the previous version of this document, RFC 4742, IANA
>   assigned the TCP port 830 as the default port for NETCONF over SSH
>  sessions.

* "Using NETCONF over the Simple Object Access Protocol (SOAP)" specification ({{Section 5 of ?RFC4743}}) states the following:

{: quote}
>    IANA assigned TCP port (833) for NETCONF over SOAP over BEEP, and TCP
> port (832) for NETCONF over SOAP over HTTPS.

It is understood that these assignments were made when the practice at that time (prior to 2011)
was to automatically assign a port number for both TCP and UDP, even if a request
was for only one of these transport protocols.

Also, many of these assignments are for protocols that are not deployed and which were tagged as Historic: {{?RFC4743}} and {{?RFC4744}}. {{?I-D.ietf-netconf-rfc4743-rfc4744-to-historic}} reported in 2012 that these two protocols:

{: quote}
> "have shown very little (if any) implementations and deployment"

Consistent with {{Section 8.2 of ?RFC6335}}, this document does not request to de-assign service names; only port numbers (for specific transport protocols) are de-assigned for better usage of available scarce resources.

# Security Considerations

Releasing back some port number soften the exhaustion risk of available port number space.

This document does not describe any protocol.

# IANA Considerations

This document requests IANA to update the "Service Name and Transport Protocol Port Number Registry"
registry {{IANA-SERVICE}} as specified in the following subsections.

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

## NETCONF over TLS Service

OLD:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconf-tls|6513|tcp|	NETCONF over TLS	| {{?RFC7589}}[RFC-ietf-netconf-over-tls13-04] |

NEW:

|Service Name |  	Port Number  |	Transport Protocol  |	Description  |	Reference  |
|-------------|:--------------:|:-----------:|-------------|:-----------:|
|netconf-tls|6513|tcp|	NETCONF over TLS	| {{?RFC7589}}{{?RFC8446}}THIS_DOCUMENT|

--- back

# Acknowledgments
{:numbered="false"}

TBC.
