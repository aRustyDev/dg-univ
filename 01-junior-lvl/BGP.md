## \#\# See [Wiki](https://github.com/aRustyDev/dg-univ/wiki/bgp) for More Info \#\#
--- 
# BGP
Border Gateway Protocol (BGP)[<sup>1</sup>][bgp-1] is a standardized exterior gateway protocol designed to exchange routing and reachability information among autonomous systems (AS) [<sup>2</sup>][ext-1] on the Internet. BGP is classified as a path-vector routing protocol, and it makes routing decisions based on paths, network policies, or rule-sets configured by a network administrator.

## How does this impact Routing?
BGP is the protocol that helps to determine & update routes between internet gateway routers.  
BGP is basically what determines the routes across the internet, so it heavily impacts routing.  

There are 2 flavors of BGP.
1. **iBGP** - Used for routing within an autonomous system (ASN)
2. **eBGP** - Used for routing across the Internet.

## Vulnerablities
There are two Major types of BGP vulnerabilities
1. [Prefix Hijack Attacks](#prefix-hijack-attacks)
2. [Route Leaks and Fat Finger Syndrome](#route-leaks-and-fat-finger-syndrome)

The risks in BGP arise from three fundamental vulnerabilities:[<sup>3</sup>][vuln-1]

1. BGP has no internal mechanism that provides strong protection of the integrity, freshness, and peer entity authenticity of the messages in peer-peer BGP communications.
2. No mechanism has been specified within BGP to validate the authority of an AS to announce NLRI information.
3. No mechanism has been specified within BGP to ensure the authenticity of the path attributes announced by an AS.

Despite all its good qualities, BGP shows several vulnerabilities which, if exploited, can cause ripple effects all over the Internet. The root of the problem is that BGP was conceived in an early development stage of the Internet when there were only a few players. Consequently, its design didn’t consider protection against deliberate or accidental errors, so malicious or misconfigured sources can potentially propagate fake routing information all over the Internet, exploiting this lack of protection. Even worse, the source of fake or malicious routing information could be either a real BGP peer or a fake peer, since BGP runs on TCP/IP and is consequently subject to every classic TCP/IP attack such as IP spoofing.  

Part of the problem can be solved applying cryptographic authentication on each BGP peer, but this won’t help stop bogus information spreading all over the Internet from legitimate misconfigured sources (route leaks), from legitimate sources which either didn’t apply cryptographic authentication at all, or from sources that deliberately announced bogus routing information (prefix hijacks).  

Solutions like Resource Public Key Infrastructure (RPKI) and BGPsec path validation have been recently standardized by IETF, but they still require the collaboration of many AS’s and thus are difficult to deploy.

### Prefix Hijack Attacks
Prefix hijacks are deliberate intentional generation of bogus routing information.

The attacker could announce routes to disrupt the services running on top of the IP space covered by the routes, or hijack the traffic to analyze confidential information flowing towards that service. The attacker could also simply announce routes with a crafted AS path to show fake neighboring connections in famous websites, like the BGP toolkit of Hurricane Electric. Or even worse, the attacker could hijack the traffic to manipulate the flowing packets at his/her will, or simply want to exploit unused routes to generate spam.

### Route Leaks and Fat Finger Syndrome
Route leaks are unintentional generation of bogus routing information caused by router misconfigurations, such as typos in the filter configuration or mis-origination of someone’s else network (fat finger). Even if unintentional, the consequences of a route leak can be the same as the prefix hijacks.

[bgp-1]: https://en.wikipedia.org/wiki/Border_Gateway_Protocol
[bgp-2]: https://blog.catchpoint.com/2019/10/25/vulnerabilities-of-bgp/

[vuln-1]: https://tools.ietf.org/html/rfc4272

[ext-1]: ASNs.md
