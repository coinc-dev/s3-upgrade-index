# s3-upgrade-index
Upload github action for sending files to s3


## Usage

Simple action for setting other S3 parameters.

```yaml
# inside .github/workflows/your-action.yml
name: Add File to Bucket
on: push

jobs:
  deploy:
    runs-on: ubuntu-latest
    
    steps:
   - uses: actions/checkout@master
   
   - name: Upload file to bucket
   uses: coinc-dev/s3-upgrade-index@1.0.2
   env:
    FILE: ./lambda.zip
    AWS_REGION: 'us-east-1'
    S3_BUCKET: ${{ secrets.AWS_S3_BUCKET }}
    S3_KEY: ${{ secrets.S3_KEY }}
    AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
    AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
    CFG: [COMMANDLINE CONFIG]
```
