## RAW Notes

Come back to this and update as you go on:
So far we have set a filter for all of the http sites that we negotiated with and we were trying to search for all of the get and post requests as they reveal the most data. After we took notes for all that we found.

We found that we had no post requests and it was all get. We documented all of those links and then set a new filter “tls” and tried to find the sites on this list but only the first client hello one. We are doing this to view the actual site the link tried to send us to. 

Filter we used for TLS was <tls.handshake.type == 1>

The new domains that I came across were 
cdn-cookieyes[.]com



log.cookieyes[.]com




virtual.urban-orthodontics[.]com




skillboxultra[.]live





iff3m7wb.technestle[.]icu
This one appears to be coming from khazikstan. FOREIGN AND SUSPICIOUS





visatayey.z19.web.core.windows[.]net
This one is coming from australia SUSSY





iplogger[.]co




ipwho[.]is


apiip[.]net


angularapiworld[.]com
This one is also australian




Based on all of these screen shots I did more research on the domains that came back flagged. I wanted to know its origin and potentially who could own it. Information on one is key and is a must in order for us to make inferences. 

Anyways we found that mainly the sus sites were coming from khazekstan and australia. 

Now we will make sure on our end to block these specific endpoitns and prevent them from being opened or access under our LAPD network and LAPD devices that are connected to this internet. 




After logging all of the domains we then wanted to check if the sever had responded back to us or did something like a server hello rather than just the normal client hello.

We found that all of the domains listed did not grant us a sever hello and didnt really mess with us. But we were able to see what was supposed to happen. What we will now do is test each domain and just scan what they are and see their origin and history and all of that. From there we can make a mini write up on each to determine if it is indeed suspicious or malicious. 


The PCAP file represents traffic generated from our sandbox environment while manually analyzing the suspicious domain. The intent was to safely replicate and observe the behavior of the site without risk to production systems. This was not a capture of live traffic from the affected end user.”

Sites that made GET commands:
	•	http://www.mysafela.org/fireworks
	•	
	•	http://msedge.b.tlu.dl.delivery.mp.microsoft.com/filestreamingservice/files/4c4fdee0-d69c-42b7-bf5c-3ec046e9dfc9?P1=1751247403&P2=404&P3=2&P4=KIOuyaltQzGUv9%2fRXevwe%2b%2fSXHyfYvf%2f5L%2fb6O%2fEjuA9bg7JGUT71DQcxatSu%2by%2f0Fb5ScE2gwu8%2bMYnHtBQiQ%3d%3d
	•	
	•	http://crl.microsoft.com/pki/crl/products/MicRooCerAut2011_2011_03_22.crl

	•	http://www.microsoft.com/pkiops/crl/MicSecSerCA2011_2011-10-18.crl
Notes on my safe la (first site negotiated with)
Upon inspecting TLS traffic and SNI fields from the pcap, no evidence of suspicious domains was found during the TLS handshake. The SNI field showed a connection to the legitimate www.mysafela.org domain, consistent with the initial alert. It’s likely the malicious redirect occurred client-side post-load via JavaScript or HTTP meta-refresh, which is not visible in encrypted traffic.

	•	HTTP (GET/POST) traffic:
These were cleartext requests you could fully inspect — and mostly went to known or benign Microsoft infrastructure or safe sites like mysafela.org.
	•	TLS (Client Hello) traffic:
These are encrypted HTTPS connections. While you can’t see the full request body, the SNI (Server Name Indication) tells you the domain it’s trying to talk to — and this is where most of the suspicious domains popped up.

