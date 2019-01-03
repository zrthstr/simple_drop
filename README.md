
# Simple Drop
Simple, fully automatized solution for receiving large quantities of third party data with the possibiollity of client side encryption. Making use of aws:s3.

# Key fetaures
* Client side encryption (e2e)
* Up to 5 TB per bucket
* Really simple & fast

# Setup & Installation
## dependencies
* working aws account
* awscli
* terraform
* bash

## install `awscli`
`% sudo pip install awscli`

## install `terraform`
### Ubuntu
`# https://askubuntu.com/a/983352 `

### arch
`% sudo pacman -S terraform`

### macOS
`% brew install terraform`

## Configure
### awscli
Add the following to you `.aws/credential`
```
[sd]
aws_access_key_id = KEYKEYKEYKEY
aws_secret_access_key = NSANSANSANSA
```

### simple_drop
```
cd aws
terraform init
```

### usage
```
% ./sdrop help 
./sdrop new|list|remove|version|help

 new                      # create new bucket
 list                     # list all buckets
 remove <bucket-id>       # remove bucket 
 version                  # print version info
 help                     # print this message
```

./sdrop new 
## enter yes or no



### how this works
`% ./sdrop add` creates the following resources with the help of terraform
 * aws_iam_access_key
 * aws_iam_user
 * aws_iam_user_policy
 * aws_s3_bucket
 
 `% ./sdrop remove` removes them :)

### Todo:
* add `./sdrop log --tail` funtion
* add `./drop new --region=region` feature

### Mybe Todo:
* Enable S3 versioning
* Enable S3 Logging
* Enable S3 replication
* Enable MFA
* Enable server side encryption
* Upload initial file as cannary for uploader to find

# limitations
max Bucket size = 5TB

