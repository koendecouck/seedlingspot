# seedlingspot
Google Cloud App Engine project holder (Python app): seedlingspot.appspot.com

## To do
Figure out some way of linking this git repo directly to the corresponding Google App Engine bucket (There only seems to be github sync support for Google Cloud Source Repo's <> App Engine buckets)...

## Workaround1: Intermediate via Google Cloud Source Repo
[!] This seems to require a billing account now.

Manually update from (github synced) Google Cloud Source Repo using Google Cloud Shell:
yes | rm -r seedlingspot
gcloud source repos clone default ~/seedlingspot
cd seedlingspot
appcfg.py -A seedlingspot -V v1 update ./

## Workaround2: Google Compute Engine instance with git-pull
Create Google Compute Engine with git clone and cronjob to periodically git-pull repo. (https://stackoverflow.com/questions/29859651/sync-github-repository-with-google-cloud-storage-bucket)
