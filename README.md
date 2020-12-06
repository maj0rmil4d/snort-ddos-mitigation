# snort-ddos-mitigation
some rules to defat dos attacks with snort


#DOS ATTACK DETECTION
alert tcp !$HOME_NET any -> $HOME_NET any (flags: S; msg:"Possible SYN DoS"; flow: stateless; threshold: type both, track by_dst, count 1000, seconds 3; sid:10002;rev:1;)
#alert tcp !$HOME_NET any -> $HOME_NET any (flags: A; msg:"Possible ACK DoS"; flow: stateless; threshold: type both, track by_dst, count 1000, seconds 3; sid:10001;rev:1;)
alert tcp !$HOME_NET any -> $HOME_NET any (flags: R; msg:"Possible RST DoS"; flow: stateless; threshold: type both, track by_dst, count 1000, seconds 3; sid:10003;rev:1;)
alert tcp !$HOME_NET any -> $HOME_NET any (flags: F; msg:"Possible FIN DoS"; flow: stateless; threshold: type both, track by_dst, count 1000, seconds 3; sid:10004;rev:1;)
alert udp !$HOME_NET any -> $HOME_NET any (msg:"Possible UDP DoS"; flow: stateless; threshold: type both, track by_dst, count 1000, seconds 3; sid:10005;rev:1;)
alert icmp !$HOME_NET any -> $HOME_NET any (msg:"Possible ICMP DoS"; threshold: type both, track by_dst, count 250, seconds 3; sid:10006;rev:1;)

#DDOS ATTACK DETECTION
alert tcp !$HOME_NET any -> $HOME_NET any (flags: S; msg:"Possible SYN DDoS"; flow: stateless; threshold: type both, track by_dst, count 100000, seconds 10; sid:100002;rev:1;)
alert tcp !$HOME_NET any -> $HOME_NET any (flags: A; msg:"Possible ACK DDoS"; flow: stateless; threshold: type both, track by_dst, count 100000, seconds 10; sid:100001;rev:1;)
alert tcp !$HOME_NET any -> $HOME_NET any (flags: R; msg:"Possible RST DDoS"; flow: stateless; threshold: type both, track by_dst, count 100000, seconds 10; sid:100003;rev:1;)
alert tcp !$HOME_NET any -> $HOME_NET any (flags: F; msg:"Possible FIN DDoS"; flow: stateless; threshold: type both, track by_dst, count 100000, seconds 10; sid:100004;rev:1;)
alert udp !$HOME_NET any -> $HOME_NET any (msg:"Possible UDP DDoS"; flow: stateless; threshold: type both, track by_dst, count 100000, seconds 10; sid:100005;rev:1;)
alert icmp !$HOME_NET any -> $HOME_NET any (msg:"Possible ICMP DDoS"; threshold: type both, track by_dst, count 100000, seconds 10; sid:100006;rev:1;)

#PING OF DEATH DETECTION
alert icmp any any -> $HOME_NET any (msg:"Possible Ping of Death"; dsize: > 10000; sid:555555;rev:1;)
