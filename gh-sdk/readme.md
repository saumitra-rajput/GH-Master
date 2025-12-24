# Help from GPT
### Your Codespace is Ubuntu Linux.

Linux installs software using:

 - package managers

- Ubuntu uses apt

Terraform is not in Ubuntu’s default repo, so we must:

- Trust HashiCorp (security)

- Tell Ubuntu where Terraform lives

- Install Terraform

## Update package list
```
sudo apt-get update

sudo apt-get install -y gnupg software-properties-common

```
Why this is needed

| Package |	Purpose |

gnupg =Verify software authenticity

software-properties-common	=Manage extra repos

## Add HashiCorp’s security key (VERY IMPORTANT)

What’s happening here (line by line)

wget → downloads HashiCorp’s public key

gpg --dearmor → converts it into system format

tee → saves it securely

🧠 Why this matters

This ensures Terraform you install is really from HashiCorp, not a fake package.

Without this → security risk.
```
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
```

## Add HashiCorp repository
What this does

Tells Ubuntu:

“Terraform packages are available at this URL”

$(lsb_release -cs) → your Ubuntu version (jammy, focal, etc.)

```
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```

## Update package list AGAIN
```
sudo apt-get update
sudo apt-get install terraform
```

## Install Terraform
```
sudo apt-get install terraform

terraform version

```


## It worked 