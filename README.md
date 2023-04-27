<!--
 # =====================================================================
# Midships Limited
# Copyright (c) 2023
# This file contains scripts/code owned by Midships Limited
#
# NOTE: Don't check this file into source control with any sensitive hard coded value.
#
# Legal Notice: Installation and use of this script is subject to
# a license agreement with Midships Limited (a company registered
# in England, under company registration number: 11324587).
# This script cannot be modified or shared with another organisation
# unless approved in writing by Midships Limited.
# You as a user of this script must review, accept and comply with the
# license terms of each downloaded/installed package that is referenced
# by this script. By proceeding with the installation, you are accepting
# the license terms of each package, and acknowledging that your use of
# each package will be subject to its respective license terms.
# =====================================================================
-->

# Certificate Manager

A tool designed to ensure that your certificates are always up-to-date and in good condition, allowing you to avoid potential security risks and maintain your website or server’s performance.

The Midships’ Certificate Manager is a tool built on Python designed to help you easily manage your keystore certificates. This tool will check if the certificates saved on a keystore have been rotated or expired and if they have been generated correctly. Our solution will inform you of all critical issues on your certificates via email, with personalized alerts.

Please contact us at sales@midships.io for further details of our solution and how it can be customised to meet your specific requirements.

### Our contact details

* **Website**: www.midships.io 
* **Email**: support@midships.io / sales@midships.io 

## Usage

### As a cronjob

To deploy the certificate manager as a cronjob, clone the repository provided by Midships. Next, add this line to your cronjob file.

```
*/30 * * * * /usr/bin/python3 /path/to/repository/sslchecker.py -c {KEYSTORE_PATH} {PASSWORD}
```

### As a container

To deploy the certificate manager as a docker container, clone the repository provided by Midships. Next, run the following commands.

```bash
# Building image
docker build --pull --rm \
  --build-arg KEYSTORE="./trustStore.jks" \
  --build-args PASSWORD="123456" \
  -f "Dockerfile" -t certificatemanager:latest "."

# Running container
docker run --rm -d -e TIME=30 certificatemanager:latest
```

## Support

For any additional support please contact Midships using the following channels:

* **Website**: www.midships.io
* **Email**: support@midships.io / sales@midships.io 

## 

*Midships Limited
Copyright (c) 2023*
