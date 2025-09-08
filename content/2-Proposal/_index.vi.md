---
title: "Cấu hình Networking"
date: "2025-06-17"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

## Tạo VPC 
Trên thanh tìm kiếm 
- Gõ ``` VPC ``` trên thanh tìm kiếm 
- Chọn vào dịch vụ VPC
![BackendCICD](/images/2-networking/Enter_vpc_in_search.png)

- Chọn vào **Your VPCs**
![BackendCICD](/images/2-networking/choose_your_vpcs.png)

- Chọn **Create VPC**
![BackendCICD](/images/2-networking/choose_create_vpc.png)

- Chọn _VPC and more_
- Nhập vào tên của VPC ```the-first-workshop-project```
![BackendCICD](/images/2-networking/choose_vpc_settings.png)
![BackendCICD](/images/2-networking/choose_vpc_settings_2.png)

- Chọn vào _Create VPC_
![BackendCICD](/images/2-networking/choose-create-vpc.png)

- Sau khi tạo xong VPC thì sẽ hiển thị như sau 
![BackendCICD](/images/2-networking/create-vpc-success.png)

- Xem VPC sau khi tạo thành công 
![BackendCICD](/images/2-networking/view-vpc-after-create-success.png)

## Tạo Security Group

#### Bastion security group 

- Chọn vào **Secutiry group**
![BackendCICD](/images/2-networking/security-group/choose-security-group.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-1.png)

- Nhập **Security group name** là ```bastion-sg```
- Nhập **Description** là ```allow access from company ip addresses```
- Chỉnh VPC thành VPC bạn vừa tạo trước đó là **the-first-workshop-project-vpc**
- Chỉnh Inbound rules có **Type** là SSH , **Source** là MyIP 
![BackendCICD](/images/2-networking/security-group/create-bastion-sg.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-2.png)

#### Public security group 

- Chọn vào **Secutiry group**
![BackendCICD](/images/2-networking/security-group/return-security-group-interface.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-1.png)

- Nhập **Security group name** là ```public-sg```
- Nhập **Description** là ```allow access from everywhere ipv4```
- Chỉnh VPC thành VPC bạn vừa tạo trước đó là **the-first-workshop-project-vpc**
- Chỉnh Inbound rules có **Type** là HTTP , **Source** là everywhere-IPv4
![BackendCICD](/images/2-networking/security-group/create-public-sg.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-2.png)

#### Private security group

- Chọn vào **Secutiry group**
![BackendCICD](/images/2-networking/security-group/return-security-group-interface.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-1.png)

- Nhập **Security group name** là ```private-sg```
- Nhập **Description** là ```allow public sg traffic to backend and frontend```
- Chỉnh VPC thành VPC bạn vừa tạo trước đó là **the-first-workshop-project-vpc**
- Chỉnh Inbound rules **Type** là HTTPS , **Source** là Custom , sau đó ấn ô tìm kiếm và tìm và chọn vào **public-sg** đã tạo trước đó 
![BackendCICD](/images/2-networking/security-group/create-private-sg.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-2.png)

- Sau khi tạo private-sg thành công , bạn sẽ được hiển thị giao diện như sau 
![BackendCICD](/images/2-networking/security-group/interface-after-create-private-sg-successfully.png)

- Tiếp theo , bạn cần ấn **Edit inbound rule** để có thể thêm 1 inbound nữa
![BackendCICD](/images/2-networking/security-group/click-edit-inbound-rule-to-private-sg.png)

- Ấn vào nút **Add rule**
![BackendCICD](/images/2-networking/security-group/click_add_rule.png)

- Tiếp theo , bạn chọn **Type** là HTTPS , **Source** là custom , bạn tìm đến private-sg trong thanh tìm kiếm , và ấn vào
- Cuối cùng ấn nút **Save rules**
![BackendCICD](/images/2-networking/security-group/add-private-sg-rule-to-inbound-of-private-sg.png)

#### Database security group

- Chọn vào **Secutiry group**
![BackendCICD](/images/2-networking/security-group/return-security-group-interface.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-1.png)

- Nhập **Security group name** là ```database-sg```
- Nhập **Description** là ```allow access from private-sg and bastion-sg```
- Chỉnh VPC thành VPC bạn vừa tạo trước đó là **the-first-workshop-project-vpc**
- Chỉnh Inbound rules
![BackendCICD](/images/2-networking/security-group/create-database-sg.png)

- Chọn **Create security group**
![BackendCICD](/images/2-networking/security-group/choose-create-security-group-2.png)
