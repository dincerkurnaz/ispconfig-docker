# ispconfig-docker
docker build -t ispconfig4 .

docker run --name ispconfig4  -e MAILMAN_EMAIL_HOST=test.com -e MAILMAN_EMAIL=test@test.com -e MAILMAN_PASS=pass -d -p 20:20 -p 21:21 -p 30000:30000 -p 30001:30001 -p 30002:30002 -p 30003:30003 -p 30004:30004 -p 30005:30005 -p 30006:30006 -p 30007:30007 -p 30008:30008 -p 30009:30009 -p 80:80 -p 443:443 -p 8080:8080 -p 53:53 -p 2222:22 ispconfig4 /start.sh

