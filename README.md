# snort-ddos-mitigation
some rules to defeat dos attacks with snort


I put my suppression list for you too 


#cloudflare ACK DDOS

suppress gen_id 1, sig_id 100001, track by_src, ip 173.245.48.0/20
suppress gen_id 1, sig_id 100001, track by_src, ip 103.21.244.0/22
suppress gen_id 1, sig_id 100001, track by_src, ip 103.22.200.0/22
suppress gen_id 1, sig_id 100001, track by_src, ip 103.31.4.0/22
suppress gen_id 1, sig_id 100001, track by_src, ip 141.101.64.0/18
suppress gen_id 1, sig_id 100001, track by_src, ip 108.162.192.0/18
suppress gen_id 1, sig_id 100001, track by_src, ip 190.93.240.0/20
suppress gen_id 1, sig_id 100001, track by_src, ip 188.114.96.0/20
suppress gen_id 1, sig_id 100001, track by_src, ip 197.234.240.0/22
suppress gen_id 1, sig_id 100001, track by_src, ip 198.41.128.0/17
suppress gen_id 1, sig_id 100001, track by_src, ip 162.158.0.0/15
suppress gen_id 1, sig_id 100001, track by_src, ip 104.16.0.0/12
suppress gen_id 1, sig_id 100001, track by_src, ip 172.64.0.0/13
suppress gen_id 1, sig_id 100001, track by_src, ip 131.0.72.0/22
