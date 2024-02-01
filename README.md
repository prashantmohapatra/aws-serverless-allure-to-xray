# Allure to Xray

**Test Reporting tool for processing results file from test automation frameworks and importing it in Xray Test Management Tool using AWS**

---
---
## Useful commands
* Install packages from the package.json file: `yarn install`
* Clean up all local packages and files:`yarn run clean`
* Clean up cdk output files only: `yarn run clean-cdk-output`
* Compare deployed stack with current state: `cdk diff`
* Emits the synthesized cloudformation template with specific stack prefix: `cdk synth {stackName}`
* Deploy this stack in AWS: `cdk deploy {stackName}`
* Destroy this stack in AWS: `cdk destroy {stackName}`

## Deployment
* Deploy Raw Data Processor Lambda to AWS account:
  `cdk deploy raw-processor-lambda`

* Deploy Xray Integrator Lambda lambda to AWS account:
  `cdk deploy xray-integrator-lambda`

* Deploy S3 buckets to AWS account:
  `cdk deploy reporting-buckets`

## Integration
Currently, this tool supports Allure report only. In order for the tool to process the results, the test frameworks need to upload corresponding allure-report.zip into Raw S3 bucket. Example of command that can be used is: 
`aws s3 cp allure-report.zip s3://allure-to-xray-raw-bucket/allure-report.zip --metadata environment=test,application=ABC,reportType=allure,projectKey=KEY`