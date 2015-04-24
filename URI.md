#URI





Helpers
-------
```
	(?<scheme>[a-z][a-z0-9\+\-\.]*)
	:((//(?<authority>((?<userinfo>([a-z0-9\-\._~]|%[0-9a-f]{2}|[!$&'\(\)\*\+,;=]|:)+)@)?(?<host>((?<regname>([a-z0-9\-\._~]|[!$&'\(\)\*\+,;=]|%[0-9a-f]{2})+)))(:(?<port>[0-9]+))?)))
		-- :((//(?<authority>(userinfo...@)?(host...)(:port)?)))
		((?<userinfo>([a-z0-9\-\._~]|%[0-9a-f]{2}|[!$&'\(\)\*\+,;=]|:)+)@)
		(?<host>((?<regname>([a-z0-9\-\._~]|[!$&'\(\)\*\+,;=]|%[0-9a-f]{2})+)))
			-- (?<host>((regname...)|(ipliteral)|(ipv4address)))
			(?<regname>([a-z0-9\-\._~]|[!$&'\(\)\*\+,;=]|%[0-9a-f]{2})+)
			(?<ipv6address>\[(([0-9a-f]{1,4})(:([0-9a-f]{1,4})){0,8})?(::(([0-9a-f]{1,4})(:([0-9a-f]{1,4})){0,7})?)?\])
			(?<ipvfuture>\[v[0-9a-f]+\.([a-z0-9\-\._~]|[!$&'\(\)\*\+,;=]|:)+\])
			(?<ipv4address>(25[0-5]|2[0-4][0-9]|1[0-9]{2}|[1-9][0-9]|[0-9])(\.(25[0-5]|2[0-4][0-9]|1[0-9]{2}|[1-9][0-9]|[0-9])){3})
		(:(?<port>[0-9]+))


unreserved: [a-z0-9\-\._~]
gen-delims: [:/\?#\[\]@]
sub-delims: [!$&'\(\)\*\+,;=]
pct-encoded: %[0-9a-f]{2}

(\?(?<query>))?(#(?<query>))?
```

Examples
--------
```
foo://username:passwor%40@example.com:8042/over/there/index.dtb?type=animal&name=narwhal#nose
urn:example:animal:ferret:nose
aaa://host.example.com:1813;transport=udp;protocol=radius
adiumxtra://www.adiumxtras.com/download/0000
mailto:foo@example.com
callto://example
callto://+12125551234
ftp://ftp.is.co.z%6A/r+f+c/rfc1808.txt
http://www.ietf!$&'()*+,;=.org/r%20f%20c/rfc2396.txt
ldap://[2001:db8::7]/c=GB?objectClass?one
mailto:John.Doe@example.com
news:comp.infosystems.www.servers.unix
tel:+1-816-555-1212
telnet://192.0.2.16:80/
urn:oasis:names:specification:docbook:dtd:xml:4.1.2

         [1080:0:0:0:8:800:200C:417A]  a unicast address
         [FF01:0:0:0:0:0:0:101]        a multicast address
         [0:0:0:0:0:0:0:1]             the loopback address
         [0:0:0:0:0:0:0:0]             the unspecified addresses
         [1080::8:800:200C:417A]       a unicast address
         [FF01::101]                   a multicast address
         [::1]                         the loopback address
         [::]                          the unspecified addresses
         [0:0:0:0:0:0:13.1.68.3]
         [0:0:0:0:0:FFFF:129.144.52.38]
         [::13.1.68.3]
         [::FFFF:129.144.52.38]
         [vA5.hola:mundo]
```
