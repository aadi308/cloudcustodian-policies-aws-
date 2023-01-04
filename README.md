# cloudcustodian-policies-aws-
Cloud Custodian enables you to manage your cloud resources by filtering, tagging, and then applying actions to them.

## Linux and Mac OS
```
python3 -m venv custodian
source custodian/bin/activate
pip install c7n       # This includes AWS support
```

Run "custodian schema <cloud-provider>.<resource>" to see the available filters and actions for each resource. For example:
```
custodian schema aws.ec2.actions
```
The policy is validated automatically when you run it, but you can also validate it separately:
```
custodian validate custodian.yml
```

You can also check which resources are identified by the policy, without running any actions on the resources:
```
custodian run --dryrun -s . custodian.yml
```
```
custodian report -s out custodian.yml
```
To run policy:
```
custodian run -s out custodian.yaml
```
