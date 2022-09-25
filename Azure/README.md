## Packer File

`packer`

<br>

## Ansible File

`wp`

<br>

## **tree 구조**

```shell
.
├── data.tf
├── db-mysql.tf
├── lb.tf
├── main.tf
├── output.tf
├── packer
│   └── centos.pkr.hcl
├── provider.tf
├── pub.tf
├── security_group.tf
├── variable.tf
├── vmss.tf
└── wp
    ├── roles
    │   ├── apache
    │   │   ├── tasks
    │   │   │   └── main.yaml
    │   │   └── vars
    │   │       └── main.yaml
    │   └── wordpress
    │       ├── tasks
    │       │   └── main.yaml
    │       ├── templates
    │       │   └── wp-config.php.j2
    │       └── vars
    │           └── main.yaml
    └── wordpress.yaml
```

