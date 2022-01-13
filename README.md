### 1. Generate id_rsa and id_rsa.pub

##### commands required
```bash
ssh-keygen -t rsa
```

##### copy pasted the terminal for the same
```console
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/saurabhchopra/.ssh/id_rsa): /Users/saurabhchopra/dev/bitwarden-deployment-automation/id_rsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/saurabhchopra/dev/bitwarden-deployment-automation/id_rsa.
Your public key has been saved in /Users/saurabhchopra/dev/bitwarden-deployment-automation/id_rsa.pub.
The key fingerprint is:
SHA256:+w6YiEp2uvCN1BPJGHxWWYx+bOpvJyJA6L6maue0JwY saurabhchopra@Saurabhs-MacBook-Pro.local
The key's randomart image is:
+---[RSA 3072]----+
|      .=.        |
| .   .o .        |
| .o o. .         |
|. .* .. +        |
|... +  +S        |
| E.o o.o .       |
|oo+++.o o        |
|+B+*ooo oo.      |
|O+Oo+. +.+o      |
+----[SHA256]-----+
```

##### change permissions of public key
```bash
chmod 400 id_rsa*
```

###2. Terraform script to create instance and deploy bitwarden

##### make sure you have terraform installed locally - Homebrew on OS X setup
```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
brew upgrade hashicorp/tap/terraform
```

##### update aws credentials, open creds file and update credentials
```bash
vi .aws/creds
```

##### copy pasted the file for the same
```console
[default]
aws_access_key_id=\<enter your aws key id here>
aws_secret_access_key=\<enter your aws secret key id here>
```

##### make sure you have main.tf file in the current directory
```bash
terraform init
terraform apply
```

##### destroy the aws infra just created
```bash
terraform destroy
```


_(Still working on this project, Please Feel Free to Contribute)_
