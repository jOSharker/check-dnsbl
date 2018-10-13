check-dnsbl
===========

Checks a list of DNS blocklists for hosts, IPs and subnet in the CIDR format.

Given any hostname or IP address or subnet, this will try to resolve the matching
IP/hostname, and check for both in all blocklists. For every match that
<<<<<<< HEAD
is found, a warning is written to STDERR and to a CSV file, and the return code will be 1.
=======
is found, a warning is written to STDERR and in a CSV file, and the return code will be 1.
>>>>>>> efced64933791294472c472c22b9f7e81b020328
Gevent is used for concurrent lookups, the number of active greenlets
is limited to (the constant) PARALLELISM.

Example usage:

```
$ ./check-dnsbl.py gmail.com 8.8.8.8/30 8.8.4.4 
WARNING: gmail.com found in spam blocklist multi.uribl.com!
WARNING: 172.217.23.101 found in spam blocklist multi.uribl.com!
WARNING: google-public-dns-a.google.com found in spam blocklist multi.uribl.com!
WARNING: 8.8.8.8 found in spam blocklist multi.uribl.com!
WARNING: 8.8.8.9 found in spam blocklist multi.uribl.com!
WARNING: 8.8.8.10 found in spam blocklist multi.uribl.com!
WARNING: 8.8.8.11 found in spam blocklist multi.uribl.com!
WARNING: google-public-dns-b.google.com found in spam blocklist multi.uribl.com!
WARNING: 8.8.4.4 found in spam blocklist multi.uribl.com!
```
