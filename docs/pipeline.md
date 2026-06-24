## Pipeline

We have one workflow which runs two jobs on every push to `main`:

- `build` which install and build both the front-end and back-end applications.
- `deploy` which deploy the front-end to AWS S3 using `aws cli` with the provided `deploy.sh` script. The back-end is deployed to Beanstalk using `ebcli`.

Note that:

-   The `deploy` job depends on the `build` job and will wait until manually approved.

