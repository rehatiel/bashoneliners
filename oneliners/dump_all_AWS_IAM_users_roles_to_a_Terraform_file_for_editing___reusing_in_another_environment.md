# dump all AWS IAM users/roles to a Terraform file for editing / reusing in another environment

## Command:
```
$ echo iamg iamgm iamgp iamip iamp iampa iamr iamrp iamu iamup | AWS_PROFILE=myprofile xargs -n1  terraforming
```

## Explanation:
Explanation
Amazon Web Services (AWS) use a collection "IAM" resources to create Users and related objects in the system. This oneliner scrapes all the relevant info and puts it into Terraform. This lets us audit our users-groups. And, it lets us re-use them in another environment!

## Limitations:
No limitations specified

