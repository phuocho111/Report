# Vue
- [Template Syntax](#template-syntax)
## Template Syntax
+ Vue.js sử dụng một cú pháp template dựa trên HTML, cho phép bạn ràng buộc (bind) một cách minh bạch cấu trúc DOM được render với dữ liệu của đối tượng Vue.
+ tạo ra 1 đối tượng và quản lí các đối tượng trong html 
### 1. text interpolation
+ Hình thức ràng buộc dữ liệu cơ bản nhất là nội suy văn bản (text interpolation) sử dụng cú pháp `“mustache”` (“ria mép” – hai dấu ngoặc nhọn)
```html
<span>Thông điệp: {{ msg }}</span>
```
+ `directive v-once` thực hiện các phép nội suy một lần (không cập nhật lại khi dữ liệu thay đổi)
```html
<span v-once>Thông điệp này sẽ không bao giờ thay đổi: {{ msg }}</span>
```
### 2. Raw HTML
+ Cú pháp mustache sẽ thông dịch dữ liệu ra thành văn bản thuần túy (plain text)
``` html
<p>Using text interpolation: {{ rawHtml }}</p>
<!--  -->
<p>Using v-html directive: <span v-html="rawHtml"></span></p>
```
### 3. Attribute Bindings 
+ Mustaches khoong thể được sử dụng bên trong html attribute, thay vào đó sẽ dùng `directive v-bind`
```html
<div v-bind:id="dynamicId"></div>
```
+ `Directive` này cũng hoạt động với các thuộc tính boolean như `disabled` và `selected`
```html
<button v-bind:disabled="isButtonDisabled">Hòn Vọng Phu</button>
```
### 4. Using JavaScript Expressions
+ Vue hỗ trợ sức mạnh toàn diện của các biểu thức JavaScript bên trong toàn bộ các ràng buộc dữ liệu (data binding)
```javascript
{{ number + 1 }}

{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

<div v-bind:id="'list-' + id"></div>
```
### 5. Directives
+  là các thuộc tính đặc biệt với prefix (tiếp đầu ngữ) `v-`, một biểu thức JavaScript đơn lẻ (ngoại trừ `v-for`)
```html
<p v-if="seen">Thoắt ẩn thoắt hiện</p>
<!--  directive v-if sẽ thêm vào hoặc bỏ 
đi phần tử <p> dựa trên tính đúng sai của giá 
trị của biểu thức seen. -->
```
+ Arguments
```html
<a v-bind:href="url"> ... </a>
<!-- href là tham số hướng dẫn directive v-bind ràng
 buộc thuộc tính href vào giá trị của biểu thức url. -->

<a v-on:click="doSomething"> ... </a>
 <!-- Viết ngắn -->
<a @click="doSomething"> ... </a>

<a v-bind:[attributeName]="url"> ... </a>
<!-- Viết ngắn -->
<a :[attributeName]="url"> ... </a>

<a v-on:[eventName]="doSomething"> ... </a>
<!-- Viết ngắn -->
<a @[eventName]="doSomething">

```
+ Modifiers: là các hậu tố (postfix) đặc biệt được đánh dấu bằng một dấu chấm, chỉ rõ rằng một directive phải được ràng buộc theo một cách đặc biệt nào đó.
```html
<form v-on:submit.prevent="onSubmit"> ... </form>
<!-- modifier .prevent hướng dẫn directive v-on gọi event
.preventDefault() khi sự kiện được kích hoạt -->
```
![Template](https://vuejs.org/assets/directive.69c37117.png)
---
## Reactivity Fundamentals
+ sử dụng `data` tùy chọn để khai báo trạng thái phản ứng của một thành phần.Giá trị tùy chọn phải là một hàm trả về một đối tượng. Vue sẽ gọi hàm khi tạo một thể hiện thành phần mới và bọc đối tượng được trả về trong hệ thống phản ứng của nó
```javascript
export default {
  data() {
    return {
      count: 1
    }
  },

  // `mounted` is a lifecycle hook which we will explain later
  mounted() {
    // `this` refers to the component instance.
    console.log(this.count) // => 1

    // data can be mutated as well
    this.count = 2
  }
}
```
### 2. Declaring Methods
+ Để thêm các phương thức vào một cá thể thành phần, chúng tôi sử dụng methodstùy chọn.
```javascript
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    }
  },
  mounted() {
    // methods can be called in lifecycle hooks, or other methods!
    this.increment()
  }
}

```
```javascript
export default {
  created() {
    // each instance now has its own copy of debounced handler
    this.debouncedClick = _.debounce(this.click, 500)
  },
  unmounted() {
    // also a good idea to cancel the timer
    // when the component is removed
    this.debouncedClick.cancel()
  },
  methods: {
    click() {
      // ... respond to click ...
    }
  }
}
```
+ `methods` có thể truy cập được từ bên trong khuôn mẫu của thành phần, sử dụng nhất làm trình nghe sự kiện
```html
<button @click="increment">{{ count }}</button>
```
---
### 3. Computed Properties 
+ Đưa quá nhiều logic vào các mẫu của bạn có thể khiến chúng trở nên cồng kềnh và khó duy trì. 
```javascript
export default {
  data() {
    return {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      }
    }
  }
}
```
```html
 <!-- muốn hiển thị các thông báo khác nhau tùy thuộc vào việc `author` đã có sách hay chưa -->
<p>Has published books:</p>
<span>{{ author.books.length > 0 ? 'Yes' : 'No' }}</span>
```
Cấu trúc lại
```javascript
export default {
  data() {
    return {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      }
    }
  },
  computed: {
    // a computed getter
    publishedBooksMessage() {
      // `this` points to the component instance
      return this.author.books.length > 0 ? 'Yes' : 'No'
    }
  }
}
```
```html
<p>Has published books:</p>
<span>{{ publishedBooksMessage }}</span>
```






