# Flexbox
### Thành phần: thùng chứa cha (flex container) và các phần tử con nằm bên trong (flex items)
### Thuộc tính:
| Thuộc tính     | khái niệm |
|---------- | -----------| 
| main axis | flex container ở trục chính dọc theo các flex-items được bố trí,không nhất thiết phải nằm ngang, mà phụ thuộc vào thuộc tính flex-direction |
| main-start, main-end | flex items được đặt trong container bắt đầu từ main-start đến main-end |
| main size | kích thước của flex items dựa theo trục main |
| cross axis | trục vuông góc với trục main và vị trí phụ thuộc vào vị trí của trục main |
| cross-start, cross-end | container bắt đầu từ cross-start đến cross-end
| cross size | kích thước của flex item dựa vào trục cross axis

---
## Flexbox Properties

1. ### display: flex
 + định nghĩa một flex container, và cũng là việc bắt buộc nếu bạn làm việc với flexbox.
```css
.container {
  display: flex; /* or inline-flex */
}
```
2. ### flex-direction:
+ dùng để chỉ định hướng hiển thì của các item, việc thay đổi hướng hiển thị flex cũng thể có thể cho phép ta thay đổi vị trí của các flex item
```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

| flex-direction | vị trí |
| -------- | ----------- |
| row | từ trái sang phải |
| row-reverse | từ phải sang trái |
|column|từ trên xuống|
|column-reverse|từ dưới lên|

3. ### flex-wrap
+ dùng để kiểm soát việc bọc các items nằm gọn trong container. Nếu chúng ta giảm chiều rộng của trình duyệt, chúng ta có thể không nhìn thấy một số item trên cùng một dòng.
```css
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```
| flex-wrap | vị trí |
| -------- | ----------- |
| nowrap | tất cả flex-items trên 1 dòng|
|wrap| các flex-items sẽ tự động xuống dòng nếu tổng width các item lớn hơn width mặc định từ trên xuống|
|wrap-reverse|các flex-items sẽ tự động xuống dòng nếu tổng width các item lớn hơn width mặc định từ dưới lên|
1. ### flex-flow: kết hợp flex-direction và flex-wrap
```css
.container {
  flex-flow: column wrap;
}
```
5. ### justify-content:
+ dùng để căn chỉnh vị trí của các items so với trục chính(main axis).
```css
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe;
}
```
| justify-content | vị trí |
| -------- | ----------- |
|flex-start|các items sẽ đặt ở flex-direction bắt đầu |
|flex-end|các items sẽ đặt ở flex-direction kết thúc|
|start| các item sẽ đặt theo hướng bắt đầu hướng chế độ viết|
|end|các item sẽ đặt theo hướng kết thúc hướng chế độ viết|
|left|các item sẽ được đặt ỏ bên trái của container|
|right|các item sẽ được đặt ỏ bên phải của container|
|center|các items được đặt ở giữa dọc theo dòng|
|space-between|sẽ chia đều khoảng cách thừa và thêm nó vào giữa các item|
|space-around|sẽ chia khoảng cách ở đầu và cuối. Khoảng cách ở đầu và cuối sẽ bằng 1 nửa khoảng cách ở giữa 2 item với nhau|
|space-evenly|sẽ chia khoảng cách đều khoảng cách giữa các item với item, item và main start, item với main end bằng nhau|

6. ### aligh-items
+ dùng để xác định cách mà các flex item được đặt trong container dọc theo chiều cross axis.
```css
.container {
  align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe;
}
```
| aligh-items | vị trí |
| -------- | ----------- |
|stretch|kéo dài lắp đầy container theo chiều cross|
|flex-start / start / self-start|items sẽ đặt ở nơi bắt đầu cros-axis kích thước không thay đổi|
|flex-end / end / self-end|items sẽ đặt ở nơi kết thúc cros-axis kích thước không thay đổi|
|center|items sẽ được đặt ở giữa cross|
|baseline|Items sẽ được đặt dựa theo các ký tự thuộc item đó.(giữa các kí tự trong items) |


7. ### align-content
+ Tương tự như justify-content chỉ khác một chỗ là thay vì căn theo trục main axis thì align-content căn theo trục cros axis.
```css
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe;
}
```
| aligh-content | vị trí |
| -------- | ----------- |
|normal| cacs items sẽ đặt ở vị trí mặt định của nó nếu không có giá trị nào được đặt|
|flex-start / start| item sẽ bắt đầu từ lề chứa cross-start của container.|
|flex-end / end|item sẽ bắt đầu từ lề chứa cross-end của container.|
|center|items sẽ nằm giữa container|
|space-between|các items sẽ chia ra dòng đầu tiên ở container trong khi dòng cuối cùng ở cuối|
|space-around|các items sẽ chia ra không gian bằng nhau xung quanh mỗi dòng
|space-evenly|các items được phân bổ đều với không gian bằng nhau xung quanh chúng|
|stretch|ines căng ra để chiếm không gian còn lại|

## Properties for the Children(flex items)
1. ### order
+ các item sẽ hiển thị theo thứ tự xuất hiện trong HTML, nhưng với thuộc tính order, bạn có thể sắp xếp lại vị trí sắp xếp của các item.
```css
.item {
  order: 5; /* default is 0 */
}
```
2. ### flex-grow
+  cho phép các phần tử giãn theo độ rộng của container.
```css
.item {
  flex-grow: 4; /* default 0 */
}
```
3. ### flex-shrink
+ ngược lại với thuộc tính flex-grow ở trên, nó không giãn ra mà lại co lại khi chúng ta thay đổi độ rộng của container.
```css
.item {
  flex-shrink: 3; /* default 1 */
}
```
4. ### flex-basis
+ sử dụng để xác định độ dài ban đầu của một item.
```css
.item {
  flex-basis:  | auto; /* default auto */
}
```
5. ### flex
+ sử dụng để gộp chung ba thuộc tính flex-grow, flex-shrink và flex-basis
```css
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```
6. ### align-self
+ có tác dụng tương tự như align-items của phần container nhưng sử dụng riêng cho từng item, bạn có thể dùng nó để đặt lại vị trí cho một số item mà align-items đã quy định.
```css
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```
## The gap property
+ kiểm soát rõ ràng không gian giữa các flex items. Nó chỉ áp dụng khoảng cách giữa các mục không nằm ở các cạnh bên ngoài.
```css
.container {
  display: flex;
  ...
  gap: 10px;
  gap: 10px 20px; /* row-gap column gap */
  row-gap: 10px;
  column-gap: 20px;
}
```