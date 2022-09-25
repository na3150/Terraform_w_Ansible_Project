### 💻 Terraform과 Ansible을 활용한 AWS Cloud로의 Wordpress 배포
## tree 구조

```
.
├── alb.tf
├── db.tf
├── main.tf
├── output.tf
├── provider.tf
├── security_group.tf
├── variable.tf
├── vpc.tf
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
<br>
<br>

