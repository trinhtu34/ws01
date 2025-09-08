---
title: "Triển khai Backend"
date: "2025-06-17"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

## Tạo Task Role 

- Bạn gõ vào thanh tìm kiếm dịch vụ ```iam```
Hình

- Chọn vào mục **Roles**
Hình

- Chọn vào **Create role** ở góc trên bên phải màn hình
Hình

- Chọn Trusted entity type là **AWS Service**
Hình 

- Trong phần **Service or use case** thì gõ vào ```container``` và chọn **Elastic Container Service**
Hình

- Chọn **Elastic Container Service Task** 
Hình

**Tại phần này tôi không chọn Policy nào bởi vì project của tôi không tương tác với resource tại AWS , nếu bạn có project tương tác với AWS thông qua SDK ví dụ là : gửi dữ liệu vào S3 thì phải cấp quyền Put Object cho role .**
- Sau đó ấn nút **Next**
Hình

- Tiếp theo nhập vào **Role name** là ```task-role-luan-van```
Hình

- Cuối cùng là kéo xuống và ấn **Create role**
Hình

## Tạo ECR Private Repository 

- Pull project từ github về bằng link ```https://github.com/trinhtu34/ws-backend-api.git```

## Tạo ECS Task Definitions

- Bạn gõ vào thanh tìm kiếm ```ecs``` để tìm dịch vụ ecs 
Hình

- Sau đó ấn vào mục **Task definitions** để tạo task definition
Hình 

- 

## Tạo ECS Cluster


## Tạo ECS Service 