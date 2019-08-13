
# Simple Drop
Simple, fully automatized solution for receiving large quantities of third-party data with the possibility of client-side encryption. Making use of aws:s3.

# Key Features
* client-side encryption (e2e)
* up to 5 TB per bucket
* really simple & fast

# How this Works
1. `sdrop` adds and removes the following resources with the help of terraform

   * aws_iam_access_key
   * aws_iam_user
   * aws_iam_user_policy
   * aws_s3_bucket
2. prints email message intended for dropping third-party providing them with credentials and instructions
 

# Setup & Installation
## Dependencies
* AWS account
* aws-cli
* terraform
* bash

## Install awscli
`% sudo pip install awscli`

## Install terraform
### Ubuntu / Debian 
`# https://askubuntu.com/a/983352 `

### arch
`% sudo pacman -S terraform`

### macOS
`% brew install terraform`

## Configure awscli
add the following to your `~/.aws/credentials`
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
## Version
```
% ./sdrop version

    ,
    )\          SD - SimpleDrop - v0.0.1
   /  \         Copyright (C) 2019 zrth1k@gmail.com
  '   D'
  ',  ,'        This program may be freely redistributed under
    `'          the terms of the GNU General Public License.
```

## Help
```
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
* create fully configured drag&drop read cyberduck "config profile file" for source
* make Terraform State remote

## Maybe Todo:
* Enable S3 versioning
* Enable S3 logging
* Enable S3 replication
* Enable MFA
* Enable server-side encryption
* Upload initial file as canary for uploader to recognize

# Limitations
max. bucket size = 5TB

