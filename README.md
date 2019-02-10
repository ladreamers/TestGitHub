# TestGitHub
Testing GitHub
================================

git clone http://..........   Sample1

================================

To update this file from git prompt:

git add README.md

git commit -m "You could add a comment"

git commit --amend -m "Updated text"

git push -u origin master

================================

git branch thirsty   <-- create branch "thirsty"

git branch   <-- show the branch

git checkout thirsty   <-- switch to this branch

git push --set-upstream origin thirsty

git merge thirsty     <-- merge branch to master

git branch -d thirsty   <-- delete branch "thirsty"

================================

git pull origin master

git log

================================

Fetch dependencies for Javascript app from Git (npm or yarn):  this will create a directory "node_modules" directory.

npm i

yarn

================================

npm install -g create-react-app    <-- install the tool

create-react-app hello-world     <-- create the app hello-world

cd hello-world

npm install --save ag-grid-community ag-grid-react react-dom-factories

npm start

---------------------------------------
openssl genrsa -des3 -out rootCA.key 2048
openssl req -x509 -new -nodes -key rootCA.key -sha256 -days 1024 -out rootCA.pem
---------------------------------------
create file with the following context:  server.csr.cnf

[req]
default_bits = 2048
prompt = no
default_md = sha256
distinguished_name = dn

[dn]
C=US
ST=RandomState
L=RandomCity
O=RandomOrganization
OU=RandomOrganizationUnit
emailAddress=
CN = localhost

---------------------------------------

Create a v3.ext file in order to create a X509 v3 certificate. Notice how we’re specifying subjectAltName here.

authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names

[alt_names]
DNS.1 = localhost

---------------------------------------------

Create a certificate key for localhost using the configuration settings stored in server.csr.cnf. This key is stored in server.key.

openssl req -new -sha256 -nodes -out server.csr -newkey rsa:2048 -keyout server.key -config <( cat server.csr.cnf )

openssl x509 -req -in server.csr -CA rootCA.pem -CAkey rootCA.key -CAcreateserial -out server.crt -days 500 -sha256 -extfile v3.ext

---------------------------------------------


