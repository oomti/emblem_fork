# Implementation log
20/11/2022 - 19:55

## Beginnings
- Create a root folder for the emblem sample application
- Create Staging, Prod and Ops project
- Set project to OPS project
- Open cloud shell
- Enable cloud build from cloud shell ( gcloud services enable cloudbuild.googleapis.com)

- Wait and reattempt

- First error skipped, new error met





27/11/2022 - 21:34

## Followup

There was an error during deployment last week.

Updated the fork with the newest version.

Reattempting running the setup shell.

Error again with service account

```
│ Error: Error creating service account: Post "https://iam.googleapis.com/v1/projects/emblem-staging-369219/serviceAccounts?alt=json&prettyPrint=false": dial tcp [2a00:1450:400c:c07::5f]:443: connect: cannot assign requested address
│
│   with module.emblem_staging.google_service_account.website_manager,
│   on ../../modules/emblem-app/iam.tf line 8, in resource "google_service_account" "website_manager":
│    8: resource "google_service_account" "website_manager" {
│
╵
╷
│ Error: Error creating service account: Post "https://iam.googleapis.com/v1/projects/emblem-staging-369219/serviceAccounts?alt=json&prettyPrint=false": dial tcp [2a00:1450:400c:c07::5f]:443: connect: cannot assign requested address
│
│   with module.emblem_staging.google_service_account.api_manager,
│   on ../../modules/emblem-app/iam.tf line 15, in resource "google_service_account" "api_manager":
│   15: resource "google_service_account" "api_manager" {
│
╵
Exited [1] at line 129 setup.sh:
   126  ops_project_id = "${OPS_PROJECT}"
   127  EOF
   128      terraform -chdir=${STAGE_ENVIRONMENT_DIR} init -backend-config="bucket=${STATE_GCS_BUCKET_NAME}" -backend-config="prefix=stage"
>>> 129     terraform -chdir=${STAGE_ENVIRONMENT_DIR} apply --auto-approve
   130
   131      # Prod Project
   132      # Only deploy to separate project for multi-project setups
```

Reattempting


