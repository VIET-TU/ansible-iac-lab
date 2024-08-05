# Dự Án Sử Dụng Ansible: Infrastructure as Code

## Mô Tả Dự Án

Dự án này sử dụng Ansible để tự động hóa việc cài đặt và cấu hình hạ tầng, triển khai ứng dụng web API chạy bằng Docker và cấu hình load balancing bằng Nginx. Các bước chính của dự án bao gồm:

1. **Chuẩn bị tài nguyên**: Bao gồm 3 server được tạo bằng Vagrant với các nhiệm vụ khác nhau.

   - Server 1: Quản lý cấu hình (IP: 192.168.56.10)
   - Server 2: Chạy container web API (IP: 192.168.56.11)
   - Server 3: Chạy Nginx cấu hình load balancing (IP: 192.168.56.12)

2. **Cài đặt Ansible**: Cài đặt Ansible trên server quản lý.

3. **Cấu hình Inventory**: Định nghĩa các máy chủ trong file `inventory.ini`.

4. **Cài đặt Docker**: Sử dụng Ansible để cài đặt Docker trên server thứ hai.

5. **Chạy container Docker**: Sử dụng Ansible để chạy các container Docker trên server thứ hai.

6. **Cài đặt Nginx**: Sử dụng Ansible để cài đặt Nginx trên server thứ ba.

7. **Cấu hình Load Balancing**: Sử dụng Ansible để cấu hình load balancing bằng Nginx trên server thứ ba.

## Thực Hiện

Các bước thực hiện được tổ chức trong các file playbook và role của Ansible để dễ dàng tái sử dụng và quản lý.

# Command

```sh
    ansible-playbook -i inventory.ini webservers-config.yml
    ansible-playbook -i inventory.ini loadbalancingservers-config.yml
```
