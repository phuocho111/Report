# GitFlow

- [Khái niệm](#khái-niệm)<br>
- [Tổng quan](#tổng-quan-về-gitflow)
    1. [Main branch](#1-main-branch)
    2. [Develop branch](#2-develop-branch)
    3. [Feature branch](#3-feature-branches)
    4. [Release branch](#4-release-branches)
    5. [Hotfix branch](#5-hotfix-branches)



>`https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow`

![Gitflow](https://wac-cdn.atlassian.com/dam/jcr:cc0b526e-adb7-4d45-874e-9bcea9898b4a/04%20Hotfix%20branches.svg?cdnVersion=447)

## Khái niệm:
- là một ý tưởng trừu tượng của 1 Git workFlow, có thể setup các branch khác nhau và merge chúng lại với nhau.
- Gitflow workflow định nghĩa là một cấu trúc phân nhánh nghiêm ngặt 
vì thể có thể quản lí các dự án lớn.

## Tổng quan về gitflow:

### 1.  Main branch:
+ Master branchs có sẵn trong git và là branchs chứa mã nguồn khởi tạo của ứng dụng.
 và các version đã sẵn sàng để realease cho người dùng có thể sử dụng.

### 2.  Develop branch:
+ Được khởi tạo từ master branches để lưu lại tất cả lịch sử thay đổi của mã nguồn. Develop branchs là merge code của tất cả các branchs feature.
+ Method:
1. Chuyển nhánh và đẩy đến serve:
```sh
    git branch develop
    git push -u origin develop
```

### 3. Feature branches:
+ Mỗi tính năng mới nên nằm trong nhánh riêng của nó, có thể được đẩy vào kho lưu trữ trung tâm  để sao lưu / cộng tác.
+ thay vì phân nhánh ra khỏi main, feature các nhánh sử dụng develop làm nhánh mẹ của chúng. Khi một tính năng hoàn tất, nó sẽ được hợp nhất trở lại trong phần phát triển.
+ không tương tác trực tiếp với nhánh main.
+ Method:
1. Tạo ra 1 feature branch:
```sh
    git checkout develop
    git checkout -b feature_branch
```
2. Sử dụng git-flow để Extensions:
```sh
    git flow feature start feature_branch
```
3. Kết thúc 1 feature branch:
+ Khi không có git-flow Extensions:
```sh
    git checkout develop
    git merge feature_branch
```
+ Khi sử dụng git-flow Extensions:
```sh
    git flow feature finish feature_branch
```
### 4. Release branches:
+ Trước khi Release một phần mềm dev team cần được tạo ra để kiểm tra lại lần cuối trước đi release sản phần để người dùng có thể sử dụng
+ theo quy ước, ở đầu tên branch sẽ thêm release- c. Bằng việc tạo branch release, vừa có thể thực hiện chỉnh sửa lần cuối trên branch này cũng như có thể tiếp tục phát triển hướng đến release kế tiếp trên branch develop.
+ Cuối cùng, khi branch release đã trở thành trạng thái có thể phát hành thì sẽ thực hiện merge vào branch master, rồi thêm tag số release đối với commit đã merge.
+ Method: 
1. Tạo Release branches dựa vào nhánh develop:
+ Không có git-flow Extensions: 
```sh
    git checkout develop
    git checkout -b release/0.1.0
```
+ Sử dung git-flow Extensions:
```sh
    git flow release start 0.1.0
    Switched to a new branch 'release/0.1.0'
```
2. Khi kết thúc release Extensions: 
+ Không có git-flow Extensions:
```sh
   git checkout main
   git merge release/0.1.0
```
+ Khi sử dụng git-flow Extensions:

```sh
   git flow release finish '0.1.0'
```

### 5. Hotfix branches:
+ Được sử dụng để chuẩn bị cho việc release production.
+ Rất giống với release branches và feature branches ngoại trừ nó dựa và main branch thay vì develop branch.
+ là nhánh trực tiếp rẽ từ nhánh main và sau khi sửa xong lỗi nó sẽ merge đồng thời main và develop và được đánh version để nhận biết lỗi
+ Ưu điểm: việc tách nhánh này ở chỗ các team members khác có thể tiếp tục công việc ở develop trong khi những người khác có thể tập trung vào fix bug của production.
+ Method:
1. Tạo ra Hotfix branches:
+ Không có git-flow Extensions:
```sh
   git checkout main
   git checkout -b hotfix_branch
```
+ Sử dụng git-flow Extensions:
```sh
   git flow hotfix start hotfix_branch
```
2. Hoàn thành 1 release branch, hotfix branch merge vào cả main và develop
+ Không có git-flow Extensions:
```sh
   git checkout main
   git merge hotfix_branch 
   git checkout develop
   git merge hotfix_branch
   git branch -D hotfix_branch
```
+ Sử dụng git-flow Extensions:
```sh
   git flow hotfix finish hotfix_branch
```