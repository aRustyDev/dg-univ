# BGP
**Sources:** [1][bgp-1],
Border Gateway Protocol (BGP) is a standardized exterior gateway protocol designed to exchange routing and reachability information among autonomous systems (AS) on the Internet. BGP is classified as a path-vector routing protocol, and it makes routing decisions based on paths, network policies, or rule-sets configured by a network administrator.

#### History
BGP was first described in 1989 in RFC 1105, and has been in use on the Internet since 1994.  
IPv6 BGP was first defined in RFC 1883 in 1995, and it was improved to RFC 2283 in 1998.  
The current version of BGP is version 4 (BGP4), which was published as RFC 4271 in 2006.  
* RFC 4271 - corrected errors, clarified ambiguities and updated the specification with common industry practices. 
  * The major enhancement was the support for CIDR and use of route aggregation to decrease the size of routing tables.
* Allows BGP4 to carry a wide range of IPv4 and IPv6 "address families".
* Also called Multiprotocol Extensions which is Multiprotocol BGP (MP-BGP).

#### How does this impact Routing?
BGP is the protocol that helps to determine & update routes between internet gateway routers.  
BGP is basically what determines the routes across the internet, so it heavily impacts routing.  

There are 2 flavors of BGP.
1. **iBGP** - Used for routing within an autonomous system (ASN)
2. **eBGP** - Used for routing across the Internet.

#### Autonomous System ASNs
**Sources:** [1][asn-1], [2][asn-2], [3][asn-3], [4][asn-4]  

#### Investigating with ASNs
#### Vulnerablities

[bgp-1]: https://en.wikipedia.org/wiki/Border_Gateway_Protocol
[asn-1]: https://en.wikipedia.org/wiki/Autonomous_system_(Internet)
[asn-2]: https://help.apnic.net/s/article/Autonomous-System-numbers
[asn-3]: https://www.iana.org/assignments/as-numbers/as-numbers.xhtml
[asn-4]: https://www.ripe.net/publications/docs/ripe-679
