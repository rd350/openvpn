# openvpn
Python script to create and archive openvpn keys.

****DO THIS BEFORE ****

 - Create  a folder /opt/catalyst/vpn-cert 
 - mv ca.crt ta.key to /opt/catalyst/vpn-cert
 - Get .ovpn file, rename it to Catalyst.ovpn and mv to above dir

1. Build keys
./vpn generate username

If the script runs successfully, you will get  a tar file in /opt/catalyst/vpn-cert. Download that and send it to the user.

2. Archive keys
./vpn revoke-full username

Revokes full access and moves keys to the archive dir.

3. Build from csr
./vpn generate-from-csr

Make sure you place the client .csr file in /var/easy-rsa/keys

4. Renew crt
./vpn renew-crt

User crt will be revoked and moved to the archive folder (Other certificates remain) and a new csr will be built. The renewed .crt file will be in /opt/catalyst/vpn-cert.

### works with python 2.7 ###
