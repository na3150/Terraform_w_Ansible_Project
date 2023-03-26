# IaC Tool을 이용한 퍼블릭 클라우드 WordPress 자동화 배포

<br>

## 1. 프로젝트 목표

IaC Tool인 Ansible과 Terraform를 사용하여 `AWS`, `Azure` 각각에 고가용성 wordpress를 배포한다. 

<br>


## 2. 프로젝트 환경

###  테스트 컴퓨터 환경

| Resource | Configuration |
| -------- | ------------- |
| CPU      | 2             |
| Memory   | 4096MB        |
| Disk     | 40GB          |
| OS       | CentOS 7      |

<br>

### 구성 관리 / 배포 도구

| Name      | Version                   |
| --------- | ------------------------- |
| Terraform | v 1.1.9 on linux_amd64    |
| Ansible   | v 2.9.27                  |
|           | python v 2.7.5 필요       |
| Azure CLI | v 2.36.0                  |
|           | Python (Linux) 3.6.8 필요 |
<br>



## 3. 서비스 아키텍처

### `AWS`

![img](https://user-images.githubusercontent.com/64996121/165767459-caa6f80b-7a87-40fd-9601-c48729a60326.png)



Bastion Host를 Public Subnet에 구성하고 Wordpress Server와 DB 서버를 Private Subnet에 구성함으로써 보안성을 향상시키고, Application Load Balancer와 AutoScaling, DB의 Multi-AZ 구성을 통해 높은 가용성을 확보한다.

<br>

**AWS 서비스 목록**

| 서비스       | 설명                                                |
| ------------ | --------------------------------------------------- |
| VPC          | 격리된 가상 네트워크 구성                           |
| EC2          | Bastion Host, WAS Server구성                        |
| RDS          | wordpress DB 용 관리형 데이터베이스 MySQL 서버 구성 |
| ALB          | wordpress EC2 인스턴스로의 트래픽 분산              |
| Auto Scaling | wordpress EC2 인스턴스의 개수를 자동으로 조정       |

<br>

### `Azure`

![img](https://user-images.githubusercontent.com/64996121/167747992-ef93f1cb-01dc-430f-9912-7f6519ba177f.png)

Packer를 통해 Ansible Playbook을 실행하여, Wordpress 구성이 완료된 AMI 이미지를 생성한다. 이후 Terraform을 이용하여 Azure에 리소스 생성 시, 시작템플릿 구성에 해당 이미지를 사용하도록 한다. 

Bastion Host와 Web Server, DB 서버를 서로 다른 Subnet에 구성함으로써 보안을 강화하고, Application Load Balancer와 VMSS를 활용하여 외부 트래픽 분산 및 클라우드의 유연성을 강화하여 가용성을 확보한다.

<br>

**Azure 서비스 목록**

| 서비스    | 설명                                                  |
| --------- | ----------------------------------------------------- |
| VNet      | 격리된 가상 네트워크 구성                             |
| VM        | Bastion Host, WAS Server구성                          |
| DB Server | wordpress DB 용 관리형 데이터베이스 MariaDB 서버 구성 |
| ALB       | wordpress VM으로의 트래픽 분산                        |
| VMSS      | wordpress VM의 개수를 자동으로 조정                   |

<br>

<br>

## OutPuts

- [Final Presenataion PPT](https://github.com/na3150/Terraform_w_Ansible_Project/blob/main/Final%20Presentation%20PPT.pdf)

