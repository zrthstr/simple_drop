
# Simple Drop
simply receive 4,5 TB third-party data files using `aws:s3`

* client-side encryption (e2e) possible, 'server-side' encryption possible to...
* 4,5 TB per bucket
* simple & fast


### needs
* Install `sdrop`
```
git clone git@github.com:zrthstr/simple_drop.git
```
* install `terraform` and `aws-cli` tools
* add `sd` AWS account to `~/.aws/credentials`
```
[sd]
aws_access_key_id = KEYKEYKEYKEY
aws_secret_access_key = NSANSANSANSA
```
* Init terraform
```
cd aws
terraform init
```


## Usage
```
% ./sdrop help 
sdrop new|list|remove|version|help
  new                        # create new bucket
  list                       # list all buckets
  remove <bucket-id>         # remove bucket 
  version                    # print version info
  help                       # print this message
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
* Enable S3 versioning, logging, replication, maybe Enable MFA
* Enable server-side encryption as default

