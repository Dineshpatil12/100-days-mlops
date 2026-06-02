Day 13 - Pull DVC-Tracked Data from Remote

Objective

Fix DVC remote authentication issues and restore the dataset from SeaweedFS remote storage.

Steps Performed

1. Checked the DVC remote configuration.

2. Identified missing authentication credentials.

3. Added the required access key and secret key.

4. Verified the remote configuration.

5. Pulled the dataset from the DVC remote.

6. Confirmed that the dataset was restored successfully.

Commands Used

cat .dvc/config

dvc remote modify s3 accesskeyid weedadmin

dvc remote modify s3 secretaccesskey weedadmin123

dvc pull

ls -l data/raw/

dvc status

Outcome

* Fixed DVC remote authentication.

* Connected successfully to SeaweedFS storage.

* Downloaded the dataset using dvc pull.

* Restored data/raw/transactions.csv locally.

* Verified that the dataset is synchronized with DVC.
