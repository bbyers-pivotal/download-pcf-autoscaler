## What does this pipeline do?

This pipeline allows you to upload the autoscaler plugin for the cf CLI into your own maven repository.

1.  To start with, create your own Docker image to use with this pipeline using the provided Dockerfile.
  * `docker build -t youruser/ubuntu-curl:latest`
  * `docker push youruser/ubuntu-curl:latest`
  * Change out the docker image referenced in `pipeline.yml`
2. Replace variables in the `params.yml` file with your info, or enter these values into Credhub. Your choice.

3. Set your pipeline and let it go!
`fly -t concourse set-pipeline -p download-pcf-autoscaler -c pipeline.yml -l params.yml`
