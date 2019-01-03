
# Simple Drop
simple fully automatized solution for receiving large quantities of client side encrypted data using aws:s3

# key fetaures


# Setup & Installation
## dependencies
* awscli
* terraform
* bash

## install `awscli`
`% sudo pip install awsclie

## install `terraform`
### Ubuntu
`https://askubuntu.com/a/983352 `

### arch
`% sudo pacman -S terraform`

### macOS
`% brew install terraform`

## Configure
### awscli
add the followingentry to you `.aws/credential`
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



### TODO
.gitignore


### usage
./sdrop new 
## enter yes or no


* maybe --region

prints all neede data and info

maybe upload file as proof so uploader knows its the right place where he is uploading the data


./sdrop list

./sdrop clear ## possible to dangerous..


### how this works
  - aws_iam_access_key
  - aws_iam_user
  - aws_iam_user_policy
  - aws_s3_bucket


### feature list
* client side/ e2e  encryption
* simple to use
* resonably secure
* really simple to use
* Using versioning
* Enable Logging
* Using replication configuration



* maybe
Enable Logging
./sdrop log --tail
limtit aws accounts permission
MFA?


# limitations
max Bucket size = 5TB

