This repo is used to host the Magento CE to OpenMage migration script.

## Prerequisites

In order to upload the generated patch files to S3, AWS CLI v2 needs to be installed:

    https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html

## Generating patch files

Before running the next script configure the AWS CLI:

    aws configure set region eu-central-1 --profile openmage.migrationpatches
    aws configure set aws_access_key_id ACCESS_KEY_HERE --profile openmage.migrationpatches
    aws configure set aws_secret_access_key SECRET_KEY_HERE --profile openmage.migrationpatches

To generate patch files for a new version just run the script from the repo root directory and follow the prompt:

    $ bash ./create-patches.sh

## Updating migrate script

    $ sed "s/SCRIPT_COMMIT_SHA_HERE/$(git log -1 --format=%H)/" migrate.sh > index.html
