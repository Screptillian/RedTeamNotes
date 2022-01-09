<ul>
  <h3>Windows Enumeration</h3>
  <li><h4> Passive Enumeration </h4></li>
  <li><h3>Wireshark</h3></li>
  <p>Use wireshark to discover NTLM protocols, LLMNR, What systems are being used for DNS servers by clients</p>
  <li><h3>Alternatives</h3></li>
  <li> TCPDump </li>
  <li> TShark </li>
  
  <li><h3>User Enumeration</h3></li>
  <p>kerbrute userenum $USERLIST -d $DOMAIN --dc $DCIP|$DCDNSNAME </p>
  <p>kerbrute userenum $USERLIST -d $DOMAIN --dc $DCIP|$DCDNSNAME --hash-file $FILESTORINGDISCOVEREDHASHES </p>
  
  <li>Impacket</li>
  <p>python impacket/examples/GetNPUsers.py -request -format hashcat -dc-ip $DCIPADDRESS -usersfile $USERSFILE -no-pass </p>
  <p>python impacket/examples/GetNPUsers.py -request -format john -dc-ip $DCIPADDRESS -usersfile $USERSFILE -no-pass </p>
  <p>python impacket/examples/GetNPUsers.py -request -format hashcat -dc-ip $DCIPADDRESS -usersfile -hashes $LMHASH:$NTHASH </p>
  
  <li><h3>enum4linux</h3></li>
  <br />
  <p> enum4linux -a $IP </p>
  <p> enum4linux -r $IP </p>
  <p> enum4linux -R <Range> $IP </p>
  <p> enum4linux -k $USERNAME </p>
  <h4> Password spraying with enum4linux </h4>
  <p> enum4linux -u $USERLIST -p $PASSLIST $IP|$IPRange </p>
  
  <li> SMBClient </li>
  <p> *** NOTE: You may have to edit your smb configuration to use smbclient on older SMB versions </p>
  <p> List Shares (No Pass): smbclient -L -N ////$IP// </p>
  <p> List Shares: smbclient -L ////$IP// </p>
  <p> Connect as user: smbclient -U $Username ////$IP// </p>
  <p> Connect as user with pass (list shares): smbclient -U $USERNAME -P $PASSWORD -L ////$IP// </p>
  <p> Connect as user with pass: smbclient -U $USERNAME -P $PASSWORD ////$IP//SHARE</p>
  
  <p><h4> Questions to Ask </h4></p>
  <li> Can I upload files? </li>
  <li> Can I download files? </li>
  <li> What permissions are available? </li>
  <li> Are permissions squashed? </li>
  <li> What AD permissions do I have? </li>
  <li> Do I belong to any default groups in AD? What are their default permissions? </li>
  
  <li><h4>Resources</h4></li>
  <p>https://steflan-security.com/smb-enumeration-guide/</p>
</ul>
