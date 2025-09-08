---
title: "Tạo cơ sở dữ liệu"
date: "2025-06-17"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

## Tạo Database

- Nhập ```rds``` vào thanh tìm kiếm , và chọn vào dịch vụ _Aurora and RDS_
_Hình_

#### Tạo subnet group

- Chọn _Create DB subnet group_
_Hình_

- Nhập vào tên , description , Chọn VPC 
_Hình_

- Tại phần Add subnet , chọn cả 2 AZs để đảm bảo HA ( High Availability ) . Tại phần chọn subnet , chọn toàn bộ **Private subnet** 
_Hình_

- Sau đó chọn _Create_
_Hình_


#### Tạo database

- Chọn mục _databases_
_Hình_

- Chọn _Create database_

#### Tạo EC2 - Bastion host

**Lưu ý : Tạo EC2 trong public subnet , cùng VPC với database , security group của RDS phải allow access cho security group của EC2 qua Port 3306 . Mục đích là để truy cập vào database để thêm cơ sở dữ liệu**

