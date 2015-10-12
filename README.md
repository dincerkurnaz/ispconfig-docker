# ispconfig-docker
docker build -t ispconfig4 .

docker run --name ispconfig4  -e MAILMAN_EMAIL_HOST=test.com -e MAILMAN_EMAIL=test@test.com -e MAILMAN_PASS=pass -d -p 20:20 -p 21:21 -p 30000:30000 -p 30001:30001 -p 30002:30002 -p 30003:30003 -p 30004:30004 -p 30005:30005 -p 30006:30006 -p 30007:30007 -p 30008:30008 -p 30009:30009 -p 80:80 -p 443:443 -p 8080:8080 -p 53:53 -p 2222:22 ispconfig4 /start.sh

# Yedek için
docker run --volumes-from ispconfig -e PASSPHRASE=pass -e AWS_ACCESS_KEY_ID=xxxxx -e AWS_SECRET_ACCESS_KEY=xxxxx -e PARAMS='--allow-source-mismatch --full-if-older-than 1W --include /var/mail/ --include /var/www/ --include /var/backup/sql/ --include /etc/' -e SRC='/' -e PARAMS_CLEAN='remove-older-than 3M --force --extra-clean' -e DEST='s3://xxxxx.amazonaws.com/bucket-name/' jerob/docker-duplicity bash /duplicity

