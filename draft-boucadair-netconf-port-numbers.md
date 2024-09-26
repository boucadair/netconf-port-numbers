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
area: AREA
workgroup: WG Working Group
keyword:
 - transport


author:
 -
    fullname: Mohamed Boucadaor
    organization: Orange
    email: mohamed.boucadair@orange.com

normative:

informative:


--- abstract

TODO Abstract


--- middle

# Introduction

TODO Introduction

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

{{Section 7 of ?RFC4744}} states the following:
{: quote}
>    IANA assigned TCP port (831) for NETCONF over BEEP.

{{Section 7 of ?RFC6242}} states the following:
{: quote}
>    Based on the previous version of this document, RFC 4742, IANA
>   assigned the TCP port 830 as the default port for NETCONF over SSH
>  sessions.

{{Section 5 of ?RFC4743}} states the following:
{: quote}
>    IANA assigned TCP port (833) for NETCONF over SOAP over BEEP, and TCP
> port (832) for NETCONF over SOAP over HTTPS.


# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

TODO Security


# IANA Considerations

This document requests IANA to update the "Service Name and Transport Protocol Port Number Registry"
registry as specified in the following subsections.

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
|netconf-beep|||	NETCONF over BEEP	| {{?RFC4744}}THIS_DOCUMENT |

A note can be added to 831/udp to indicate that the port number used to be assigned to NETCONF over BEEP but released by THIS_DOCUMENT.

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
|netconfsoaphttp	| | |	NETCONF for SOAP over HTTPS|	{{?RFC4743}}THIS_DOCUMENT |
|netconfsoapbeep	| | |	NETCONF for SOAP over BEEP |	{{?RFC4743}}THIS_DOCUMENT |

A note can be added to 832/831 to indicate that the port numbers used to be assigned to NETCONF over SOAP but released by THIS_DOCUMENT.

## NETCONF TLS Service

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
