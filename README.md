# aws_ec2

## Description:
Downloading the content of this repository gives you possibility to create your own EC2 image with packer tool.
Note that instructions below are tested on ubuntu only.

## Requierments:
You need packer tool installed on your machine.

## Files:
- `ec2.json` - file which **Packer** use in order to create our image


## Instructions HOW to install `Packer`
- Download **Packer** from [here](https://www.packer.io/)
- Click on following link: [Install Packer](https://www.packer.io/intro/getting-started/install.html) 

## Instructions HOW to build your image with **Packer**
- Download the content of **berchev/aws_ec2** repository: `git clone https://github.com/berchev/aws_ec2.git`
- Change to downloaded **aws_ec2** directory: `cd aws_ec2`
- You need to export your **aws_access_key** and **aws_secret_access_key** as an env variable in linux:
  ```
  export AWS_ACCESS_KEY_ID="XXXXXXXXXXXXXX"
  export AWS_SECRET_ACCESS_KEY="XXXXXXXXXXXXXXXXXXXXXXXX"
  ```
- Note that current `ec2.json` configuration will create EC2 image in **us-west-2** region. If you do not want that, you need to specify region by your choice. 
- Note taht change of the region will led to change in the image (`source_ami`). The `source_ami` specified in ec2.json file could be not available in the region chosed by you.
That's why if you chnage the **region** you may need to change the **source_ami**, too.
- Run command: `packer build template.json` and wait the script to finish. You will receive notification similar to this one:
  ```
  ==> Builds finished. The artifacts of successful builds are:
  --> amazon-ebs: AMIs were created:
  us-west-2: ami-02e3eb1cf3d4876de
  ```
