
# Simple Drop
simply receive max 4,5 TB third-party data via `aws:s3`
* client-side encryption (e2e) possible
* serverside encryption maybe possible to..
* up to 5 TB per bucket
* really simple & fast

## uage
1. `sdrop` adds and removes the following resources with the help of terraform

   * aws_iam_access_key
   * aws_iam_user
   * aws_iam_user_policy
   * aws_s3_bucket
2. prints email message intended for dropping third-party, inculding including credentials and instructions
 

# Setup & Installation
## Dependencies
* AWS account
* aws-cli
* terraform
* bash

## Install awscli, terraform 
`% sudo pip install awscli`
`% sudo pacman -S terraform`
`% brew install terraform`

## Configure awscli
add the `sd` resource to your `~/.aws/credentials`
```
[sd]
aws_access_key_id = KEYKEYKEYKEY
aws_secret_access_key = NSANSANSANSA
```

### simple_drop
```
git clone git@github.com:zrthstr/simple_drop.git
cd aws
terraform init
```

# Usage
## Version & Help
```
% ./sdrop version

    ,
    )\          SD - SimpleDrop - v0.0.1
   /  \         Copyright (C) 2019 zrth1k@gmail.com
  '   D'
  ',  ,'        This program may be freely redistributed under
    `'          the terms of the GNU General Public License.


% ./sdrop help 
./sdrop new|list|remove|version|help

 new                      # create new bucket
 list                     # list all buckets
 remove <bucket-id>       # remove bucket 
 version                  # print version info
 help                     # print this message
```
## Add New Drop
```
% ./sdrop new
Creating new bucket: simple-drop-xxxxxxxxxxxxxxxx.s3.amazonaws.com
# confirm yes or no
```
## List all Drops
```
% ./sdrop list 
Listing buckets
BUCKET   yyyyy.yyyyy    yyyyyyyyyyyyyyyyyyyyyyyyy
OWNER	 nnnnn.mmmmm	xxxxxxxxxxxxxxxxxxxxxxxxx
...
```
## Remove Drop
```
% ./sdrop remove 123456789
Removing Bucket: s3-xxxxxx.tf
# confirm: yes
Removing aws_iam_access_key, aws_iam_user, aws_iam_user_policy, aws_s3_bucket
```

## Todo:
* add `./sdrop log --tail` functionality
* add `./drop new --region=region` feature
* send cyberduck/filezilla config + credentials via email template
* maybe make Terraform State remote
* Enable S3 versioning, logging, replication, maybe Enable MFA
* Enable server-side encryption as default
* maybe Upload initial file as canary for uploader to recognize

# Limitations
max. bucket size = 5TB

