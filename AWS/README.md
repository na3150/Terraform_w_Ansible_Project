### π» Terraformκ³Ό Ansibleμ νμ©ν AWS Cloudλ‘μ Wordpress λ°°ν¬
## tree κ΅¬μ‘°

```
.
βββ alb.tf
βββ db.tf
βββ main.tf
βββ output.tf
βββ provider.tf
βββ security_group.tf
βββ variable.tf
βββ vpc.tf
βββ wp
    βββ roles
    β   βββ apache
    β   β   βββ tasks
    β   β   β   βββ main.yaml
    β   β   βββ vars
    β   β       βββ main.yaml
    β   βββ wordpress
    β       βββ tasks
    β       β   βββ main.yaml
    β       βββ templates
    β       β   βββ wp-config.php.j2
    β       βββ vars
    β           βββ main.yaml
    βββ wordpress.yaml
```
<br>
<br>

