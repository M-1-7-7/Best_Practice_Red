# Rainbow Tables
This tutorial will provide a full walkthrough of how to attack passwordward hashes offline using a rainbow attack, including salted hashes

A rainbow table is where you have a pre defined password list and you have used a tool such as `` to generate respective hashes into a file. from there you pass those target hashes to the hash file that you are trying to crack and any matches will be identified

### Basic rainbow table list generation
1. install [knotty.php](https://github.com/prodigiousMind/knotty)
2. have a wordlist you would like to use to target the hashes
3. execute `for (pt in $(cat plaintext-wordlist); do php knotty.php plaintext=${pt} algo=all format=3;done) > reinbow-table` you can look into the readme and stuff to be more specific about format and algorithem values
![image](https://github.com/user-attachments/assets/5c9f961f-9702-4d81-8212-13a60165ce78)

### Crack the hashed
1. execute `(for hash in $(cat compromised-db); do grep ${hash} rainbow-table ; done) > cracked-hashes`
2. and now the hashes that are successfully crakced can be found in the `cracked-hashes` file
![image](https://github.com/user-attachments/assets/ecd02fbc-3d66-441e-8487-37f0924547aa)
