# Development environment

 1. [Cài đặt ubuntu](#1-cài-đặt-ubuntu)
 2. [NVM](#2nvm)
 3. [git](#3cài-đặt-git)
 4. [vue](#4cài-đặt-vue-js)


## 1. Cài đặt Ubuntu:
[Link tiếng anh](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

[Link Tiếng việt](https://quantrimang.com/cach-cai-ubuntu-song-song-voi-windows-bang-usb-148331)

### B1: 
+ Download an Ubuntu Image:
>https://ubuntu.com/download/desktop
+ Create a Bootable USB stick
>https://rufus.ie/vi/

### B2: 

1. Đầu tiên, chọn ổ USB được gắn vào hệ thống của bạn mà bạn muốn sử dụng
2.Bước thứ hai là chọn tệp ISO đã tải xuống của Jammy JellyFish.
3. nhấn nút start, khi hoàn thành nhấn close

### B3: Chia ổ đĩa
1. Click chuột phải vào `this PC` > `Manage`
2.  click vào mục `Disk Management` để hiển thị danh sách các ổ đĩa
3. Click chuột phải vào ổ đĩa chọn rồi nhấn Shrink Volume… để tạo phân vùng trống dùng để cài Ubuntu.
4.  Tại phần `Enter the amount of space to Shrink in MB`, nhập dung lượng phân vùng cài Ubuntu,  Nhấn vào `Shrink`.

### B4: 
1. Cắm USB đã boot vào máy tính rồi nhấn các phím tắt truy cập Boot Options (F12).
2. Trong giao diện chọn thiết bị boot nhấn` USB Storage Device` để chọn thiết bị USB.
3. Xuất hiện giao diện mới chọn Install Ubuntu để cài đặt Ubuntu trên Windows.

### B5: Set Up Ubuntu
1. chọn ngôn ngữ: `Tiếng việt`
2. Preparing to install Ubuntu: `nhấn continue`
3.  Installation type: `Something else` ( Để cài song song và tách biệt hoàn toàn với Windows )
4. Installation type (tiếp theo):  chọn `free space` ( phần trống được chia ra từ ổ đĩa ) và nhấn dấu `+`.
5. Xuất hiện giao diện `Create partition` để tạo phân vùng Swap cho Ubuntu hỗ trợ RAM. 
+ Size chọn dung lượng phân vùng Swap gấp đôi dung lượng RAM.
+ Type for the New partition: chọn `Logical`
+ Localtion for the new partition: `Beginning of this space`
+ Ở Use as: chọn `swap area` và 
6. Tiếp tục chọn `free space` và nhấn dấu `+`
+ giữ nguyên Size \
+ Type for the new partition: chọn `Primary`
+  Location for the new partition: chọn `Beginning of this space`
+ Use as: chọn `Ext4 journaling File sytem`
+ Mount point: chọn `/`
7. Phân vùng mới vừa tạo có `Type là ext4`, click vào đó rồi chọn `Install now`.
8. Where are you: Nhấn chọn `vào địa điểm vị trí hiện tại` rồi nhấn vào `Continue` để tiếp tục.
9. Keyboard layout: Chọn ngôn ngữ bàn phím là `tiếng Anh`
10. Who are you: nhập thông tin bằng tiếng anh
11. Restart Now

### Lưu ý: trong quá trình cài đặt nếu hệ điều hành Windows hay hệ điều hành khác bị mất Boot 

>https://blogtinhoc.com/cach-cai-grub-customizer-de-chinh-sua-grub-tren-ubuntu.html

----------------------------------------

## 2.NVM

1. ### Khái niệm:
- nvm (Node Version Manager) là package giúp quản lí nhiều phiên bản của node.
- khi tạo các project trên các phiên bản node khác nhau thay vì cài lại phiên bản thì nvm sẽ giúp quản lí các phiên bản và chuyển đổi các phiên bản qua lại.
2. ### Cài đặt NVM:
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
```sh
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
3. ### chuyển đổi các Version node

+ Cài đặt version node:
```sh
nvm install <version node>
```
+ Set default node
```sh
nvm alias default <version node>
```
+ Sử dụng node
```sh
nvm user <version node>
```
+ liệt kê các phiên bản node
```sh
nvm ls-remote
```
+ Muốn nhìn thấy version đã cài đặt:
```sh
nvm ls
```
4. ### Tham khảo:
>https://github.com/nvm-sh/nvm#set-default-node-version

-----------------------------------
## 3.Cài đặt Git
1. ### Cài đặt git với apt
```sh
sudo apt update 
sudo apt install git
```
2. ### Kiểm tra phiên bản: 
```sh
git --version
```

--------------------------------
## 4.Cài đặt Vue js:
1. Install
```sh
npm install -g @vue/cli
# OR
yarn global add @vue/cli
```
2. kiểm tra phiên bản
```sh
vue --version
```
3. Tạo app vue
```sh
vue create <Tên app>
```
---
### Questions:
[Nvm](#2nvm)



