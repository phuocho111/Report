# Vue
  [Basis & Core concepts](#basis--core-concepts)
- [Template Syntax](#template-syntax)
- [Reactivity Fundamentals](#reactivity-fundamentals)
- [Method, computed, watcher](#method-computed-watcher)
- [Class and Style Bindings](#method-computed-watcher)
- [Conditional Rendering](#conditional-rendering)
- [list Rendering](#list-rendering)
- [Event Handling](#event-handling)
- [lifecycle hooks](#lifecycle-hooks)

[Vue Component](#vue-component)
# Basis & Core concepts
## Template Syntax
+ Vue.js sử dụng một cú pháp template dựa trên HTML, cho phép bạn ràng buộc (bind) một cách minh bạch cấu trúc DOM được render với dữ liệu của đối tượng Vue.
+ tạo ra 1 đối tượng và quản lí các đối tượng trong html 
### 1. text interpolation
+ Hình thức ràng buộc dữ liệu cơ bản nhất là nội suy văn bản (text interpolation) sử dụng cú pháp `“mustache”` (“ria mép” – hai dấu ngoặc nhọn)
```html
<span>Thông điệp: {{ msg }}</span>
```
+ `directive v-once` cho dù các key trong data bị thay đổi nội dung nhưng sẽ không thay đổi nội dung ban đầu
```html
<span v-once>Thông điệp này sẽ không bao giờ thay đổi: {{ msg }}</span>
```
### 2. Raw HTML
+ Cú pháp mustache sẽ thông dịch dữ liệu ra thành văn bản thuần túy (plain text)
+ nếu muốn in ra mã html thì gắn `v-html`
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
## Method, computed, watcher

1. Methods là tập hợp những functions,dùng để xử lý khi bắt sự kiện với DOM hoặc để tái sử dụng code, Methods cho phép truyền vào tham số
- với `{{data}}` method không biết được nó cần thực thi khi nào,  nó sẽ luôn thực thi khi re-render(vì thế sinh ra computed)
2. Computed hữu dụng khi thao tác với các dữ liệu đã tồn tại, nó làm việc với `data` và lấy dữ liệu các đối tượng xử lí cho ra kết quả ở `{{}}` Computed không cho phép truyền tham số
3. Watched có thể giám sát và lắng nghe được sự thay đổi của các đối tượng (message)

|  | Methods | computed | watcher |
| --- | --- | --- | --- |
| cho phép có tham số | có | không | có |
| khả năng Cached| không | có | N/A |
| phạm vi thực hiện | local cho tới component | Local cho tới component, nhưng có thể lấy / thực hiện tính toán với các biến từ props, stores, v.v. | Có thể xem các biến local hoặc store variables và react với các thay đổi |
|Thực hiện khi | Thành phần phụ thuộc thay đổi | Bất kì thay đổi nào (re-render) | 	Thuộc tính, đối tượng được giám sát bị thay đổi |
| Nên sử dụng khi | Cần đến một hàm thuần túy hoặc cần truyền tham số vào | Khi muốn thao tác với dữ liệu trong instance hay tham chiếu giá trị từ template, hạn chế tính toán lại, lắng nghe thay đổi của nhiều thuộc tính dữ liệu | Xử lí khi muốn lắng nghe dữ liệu thay đổi nhiều, liên tục, hay lắng nghe một thuộc tính cụ thể của object, hoặc là bạn muốn xem một thuộc tính dữ liệu cho đến khi nó đạt đến một giá trị cụ thể nào đó rồi thao tác với nó |

```html
<template>
	<div id="app">
		<img alt="Vue logo" src="./assets/logo.png">
		<p>{{ upperMessage }}</p>
		<button @click="showMessage">Click me</button>
	</div>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			message: 'Cảm ơn bạn đã theo dõi bài viết này!',
		}
	},
	methods: {
		showMessage() {
			this.message = "Message đã thay đổi!";
		}
	},
	computed: {
		upperMessage() {
			return this.message.toUpperCase();
		}
	},
	watch: {
        upperMessage() {
            console.log('Đã lắng nghe được message thay đổi!');
        }
    }
}
</script>
```
## Template Ref
+ ref cho phép chúng được tham chiếu trực tiếp đến một phần tử DOM cụ thể hoặc cá thể thành phần con sau khi nó được gắn kết

```html
<script>
export default {
  mounted() {
    this.$refs.input.focus()
  }
}
</script>

<template>
  <input ref="input" />
</template>
```
1. `ref` trong `v-for`
+ Khi ref được sử dụng bên trong v-for, giá trị ref thu được sẽ là một mảng chứa các phần tử tương ứng
```html
   <input :ref="(el) => { /* assign el to a property or ref */ }">
```
+ sử dụng một :`ref` ràng buộc động để chúng tôi có thể chuyển cho nó một hàm thay vì một chuỗi tên tham chiếu. Khi phần tử không được gắn kết, đối số sẽ là `null`
```html
// LoginModal
<template>
    <form>
       <Form ref="formRef" />
       <button>Login</button>
    </form>
</template>

<script>
export default {
    methods: {
       handleLogin() {
           this.$refs.formRef.validateEmail();
           this.$refs.formRef.validatePassword();
            const data = this.$refs.formRef.data;
           // Login logic
       }
    }
}
//di chuyển hết data ở component <Form /> lên component <LoginModal /> rồi truyền nó xuống component <Form />
</script>
```
---
## Class and Style Bindings
### 1. Binding Inline Class
+ Binding to Objects
```html
<div :class="{ active: isActive }"></div>
<!-- sự hiện diện của active lớp sẽ được xác định bởi 
tính trung thực của thuộc tính dữ liệu isActive -->
```
```javascript
data() {
  return {
    isActive: true,
    hasError: false
  }
}
```
```html
<div
  class="static"
  :class="{ active: isActive, 'text-danger': hasError }"
></div>
```
Hiển thị
```html
<div class="static active"></div>
```
+ Binding to Arrays

```html
<div :class="[activeClass, errorClass]"></div>
```
toán tử 3 ngôi
```html
<div :class="[isActive ? activeClass : '', errorClass]"></div>
```
### 2. Binding Inline Styles 
+ Binding to Objects
```html
<div :style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>
```
```javascript
data() {
  return {
    styleObject: {
      color: 'red',
      fontSize: '13px'
    }
  }
}
```
+ Binding to Arrays
```html
<div :style="[baseStyles, overridingStyles]"></div>
```
+ Multiple Values
```html
<div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }"></div>
```
---
## Conditional Rendering
### 1. v-if
+ được sử dụng để hiển thị một khối có điều kiện. trả về một giá trị trung thực.
### 2. v-else
+ chỉ thị để chỉ ra một "khối khác" cho v-if:
```html
<button @click="awesome = !awesome">Toggle</button>

<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
```
### 3. v-else-if
+  đóng vai trò như một "khối nếu khác" cho `v-if`. Nó cũng có thể được xâu chuỗi nhiều lần
```html
<div v-if="type === 'A'">
  A
</div>
<div v-else-if="type === 'B'">
  B
</div>
<div v-else-if="type === 'C'">
  C
</div>
<div v-else>
  Not A/B/C
</div>
```
### 4. v-if trên tempplate
+ muốn chuyển đổi nhiều hơn một phần tử, sử dụng `v-if` trên một`<template>`phần tử, phần tử này đóng vai trò như một trình bao bọc vô hình.
```html
<template v-if="ok">
  <h1>Title</h1>
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
</template>
```
### 5. v-show
+ `v-show` chỉ chuyển đổi thuộc tính display CSS của phần tử (ẩn hiện element).
+ `v-show` không hỗ trợ `<template>` phần tử, cũng như không hoạt động với `v-else`
+ `v-hide` ngược lại `v-show`

```html
<h1 v-show="ok">Hello!</h1>
```
---
## List Rendering
### 1. v-for
+ `v-for` chỉ thị để hiển thị danh sách các mục dựa trên một mảng. Lệnh `v-for `yêu cầu một cú pháp đặc biệt ở dạng item in items, đâu itemslà mảng dữ liệu nguồn và itemlà một bí danh cho phần tử mảng 
+ có thể sử dụng oflàm dấu phân tách thay vì in, để nó gần với cú pháp của JavaScript dành cho trình vòng lặp
### 2. v-for với object
+ có thể sử dụng `v-for` để lặp qua các thuộc tính của một đối tượng. Thứ tự lặp lại sẽ dựa trên kết quả của việc gọi `Object.keys()` đối tượng
```javascript
data() {
  return {
    myObject: {
      title: 'How to do lists in Vue',
      author: 'Jane Doe',
      publishedAt: '2016-04-10'
    }
  }
}
```
```html
<ul>
  <li v-for="value in myObject">
    {{ value }}
  </li>
</ul>
```
### 3. v-for with a Range
+ `v-for` cũng có thể nhận một số nguyên. Trong trường hợp này, nó sẽ lặp lại mẫu nhiều lần, dựa trên một loạt các 1...n.
```html
```
### 4. v-for trên template
+ có thể sử dụng `<template>` thẻ với `v-for` để hiển thị một khối gồm nhiều phần tử.
```html
<ul>
  <template v-for="item in items">
    <li>{{ item.msg }}</li>
    <li class="divider" role="presentation"></li>
  </template>
</ul>
```
### 5. v-for với v-if
+ Khi chúng tồn tại trên cùng một nút, `v-if` có mức độ ưu tiên cao hơn `v-for`. Điều đó có nghĩa là `v-if` điều kiện sẽ không có quyền truy cập vào các biến từ phạm vi của `v-for`
```html
<li v-for="todo in todos" v-if="!todo.isComplete">
  {{ todo.name }}
</li>
```
khắc phục bằng cách chuyển `v-for` sang thẻ gói `<template>`
```html
<template v-for="todo in todos">
  <li v-if="!todo.isComplete">
    {{ todo.name }}
  </li>
</template>
```
### 6. Maintaining State with key
+ để nó có thể theo dõi danh tính của từng nút, cần cung cấp một keythuộc tính duy nhất cho mỗi mục
```html
<div v-for="item in items" :key="item.id">
  <!-- content -->
</div>
```
### 7. Mutation Methods
`push()`
`pop()`
`shift()`
`unshift()`
`splice()`
`sort()`
`reverse()`

```javascript
data() {
  return {
    sets: [[ 1, 2, 3, 4, 5 ], [6, 7, 8, 9, 10]]
  }
},
methods: {
  even(numbers) {
    return numbers.filter(number => number % 2 === 0)//2,4,6,8,10
  }
}
```
```html
<ul v-for="numbers in sets">
  <li v-for="n in even(numbers)">{{ n }}</li>
</ul>
```
---
##  Event Handling
### 1. Listening to Events
  + sử dụng v-on (@) để lắng nghe các sự kiện DOM và chạy một số JavaScript khi chúng được kích hoạt, Cú pháp sẽ là v-on:[event]="[hander]"
```javaScript
methods: {
  say(message) {
    alert(message)
  }
}
```
```html
<button @click="say('hello')">Say hello</button>
<button @click="say('bye')">Say bye</button>
```
1. Event Modifiers
+ là một nhu cầu rất phổ biến để gọi `event.preventDefault()`hoặc `event.stopPropagation()` bên trong trình xử lý sự kiện
`.stop`
`.prevent`
`.self`
`.capture`
`.once`
`.passive`
```javascript
handleSubmit (event) {
  event.preventDefault();
}
```
->event modifier
```javascript
<form @submit.prevent="handleSubmit"></form>
```
---
## Form Input Bindings
+ `v-model` là chức năng được sử dụng rất nhiều khi tạo form sử dụng Vue.js, liên kết element với property
```html
<input v-model="searchText">
<input :value="searchText" @change="searchText = $event.target.value">
```
+  `v-model` sẽ bỏ qua các giá trị ban đầu, "checked" hoặc "selected" attribute được tìm thấy trên bất kì form elements nào. Nó sẽ luôn luôn xử lý các dữ liệu của Vue instance như là những dữ liệu luôn đúng
+ `v-model` cũng hỗ trợ ràng buộc giá trị của các giá trị không phải là chuỗi!
```html
<div>Selected: {{ selected }}</div>

<select v-model="selected" multiple>
  <option>A</option>
  <option>B</option>
  <option>C</option>
```
----
## Lifecycle hooks
###  sơ đồ vòng đời
+  Lifecycle của một instance sẽ gồm
1. khởi tạo một đối tượng Vue
2. Gắn kết vào DOM
3. Cập nhập DOM khi dữ liệu thay đổi
4. Hủy instance

### 1. giai đoạn khởi tạo
+ beforeCreate hock chạy mỗi khi khởi tạo instance, tại  thời điểm này data, event chưa được thiết lập (không thể this từ data)
+ created hook được chạy khi data, event đã thiết lập thành công ( có thể this từ data)
```javascript
new Vue({
    el: "#app",
    data: {
        content: "Lifecycle Hooks",
    },
    beforeCreate () {
        console.log('before create')
        console.log(this.content) // khi này this.content trả về undefined vì data chưa được nhận (observe).
    },
    created () {
        console.log('created')
        console.log(this.content) // khi này this.content trả về  "Lifecycle Hooks" vì quá trình observe data, thiết lập event đã hoàn thành.
    }
})
```

### 2. Giai đoạn gắn kết DOM
+ beforeMount hook sẽ chạy sau khi data, event được thiết lập và trước khi gắn kết vào DOM. Trong hook này chúng ta vẫn chưa - truy cập được phần tử trong DOM.
+ mounted hook: giai đoạn này, mounted hook cho phép truy cập vào phần tử DOM khi vừa gắn lên
```javascript
new Vue({
    el: "#app",
    data: {
        content: "Lifecycle Hooks",
    },
    beforeMount () {
        console.log('before mount')
        console.log(this.$el.textContent) // lỗi vì chưa gắn kết DOM vì vậy chưa thể truy cập đến các thành phần trong DOM ở console.log sẽ hiển thị ra 
    },
    mounted () {
        console.log('mounted')
        console.log(this.$el.textContent) // khi này this.$el đã gắn kết với DOM, lúc này có thể truy cập được tới các thành phần trong DOM 
    }
})
```
### 3. Giai đoạn cập nhật DOM khi dữ liệu thay đổi:
+ beforeUpdate hook: sau khi đối tượng đã được gắn vào DOM, khi dữ liệu thay đổi, và trước khi render, patch lại và hiển thị ra cho người dùng.
+ updated hook: chạy ngay sau khi beforeUpdate. Sử dụng khi bạn cần truy cập DOM sau khi thay đổi thuộc tính. dữ liệu ở beforeUpdate và updated là như nhau

### 4. Giai đoạn huỷ instance:
+ beforeDestroy hook: là giai đoạn trước khi instance bị hủy, đây là nơi để quản lí tài nguyên xóa tài nguyên, dọn dẹp các component
```javascript
var vm = new Vue({
    el: "#app",
    data: {
        content: "Lifecycle Hooks"
    },
    beforeDestroy () {
         this.content = null
         delete this.content
    },
})
```
+ destroyed hook: thời điểm này, mọi thành phần đã được hủy bỏ hết. Khi console.log() đối tượng this sẽ không tính hay dữ liệu.
```javascript
var vm = new Vue({
    el: "#app",
    data: {
        content: "Lifecycle Hooks"
    },
    destroyed () {
        console.log(this) //thời điểm này sẽ không nhận được gì ở console.
    },
})
```
---

# Vue component

### 1. sử dụng một thành phần con, chúng ta cần nhập nó trong thành phần mẹ
```javascript
<script>
import ButtonCounter from './ButtonCounter.vue'

export default {
  components: {
    ButtonCounter
  }
}
</script>

<template>
  <h1>Here is a child component!</h1>
  <ButtonCounter />
</template>
```
### 2. Listening to Events (style)
```html
<BlogPost
  ...
  @enlarge-text="postFontSize += 0.1"
 />
 ```
 thành phần con có thể tự phát ra một sự kiện bằng cách gọi $emit phương thức tích hợp sẵn , chuyển tên của sự kiện:
 ```html
 <!-- BlogPost.vue, omitting <script> -->
<template>
  <div class="blog-post">
    <h4>{{ title }}</h4>
    <button @click="$emit('enlarge-text')">Enlarge text</button>
  </div>
</template>
```
### chức năng: 
+ tái sử dụng nhiều lần
+ truyền dữ liệu giữa các component
1. parent -> child(props)
2. child -> parent($emit)
---
# Vue Props
+ để truyền dữ liệu từ phần tử cha xuống các phần tử con ( ràng buộc 1 chiều )
+  v-bind:[prop-name] để truyền dữ liệu vào các component con
+  Prop được sử dụng để chuyển vào một giá trị ban đầu; sau đó thành phần con muốn sử dụng nó làm thuộc tính dữ liệu cục bộ. 
+  Có type thể là một trong các hàm tạo gốc sau: String, Number, Boolean, Array, Object, Date, Function, Symbol.
```javascript
export default {
  props: ['initialCounter'],
  data() {
    return {
      // counter only uses this.initialCounter as the initial value;
      // it is disconnected from future prop updates.
      counter: this.initialCounter
    }
  }
}
```
---
# Vue Router
### 1. cài đặt vue router
npm
```sh
npm install vue-router@3
```
yarn
```sh
yarn add vue-router@4
```


### 2. Khởi tạo 1 Route mới
```html
<script src="https://unpkg.com/vue@3"></script>
<script src="https://unpkg.com/vue-router@4"></script>

<div id="app">
  <h1>Hello App!</h1>
  <p>
    <!-- use the router-link component for navigation. -->
    <!-- specify the link by passing the `to` prop. -->
    <!-- `<router-link>` will render an `<a>` tag with the correct `href` attribute -->
    <router-link to="/">Go to Home</router-link>
    <router-link to="/about">Go to About</router-link>
  </p>
  <!-- route outlet -->
  <!-- component matched by the route will render here -->
  <router-view></router-view>
</div>
```
### 1. router-link
+ hiển thì các thành phần mà chúng ta đã thiết đặt routes giống như thẻ `<a>` 
```html
<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-link :to="{ name: 'Hello' }">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-view></router-view>
  </div>
</template>
```
+ 2 thẻ route-link
Thẻ thứ nhất: sử dụng name của Route đã được định nghĩa tại /src/router/index.js

Thẻ thứ hai: chỉ định đường dẫn cố định mà chúng ta muốn liên kết đến.
### 2. router-view
+ hiển thị thành phần tương ứng với url
```javascript
// Home.vue
export default {
  computed: {
    username() {
      // We will see what `params` is shortly
      return this.$route.params.username
    },
  },
  methods: {
    goToDashboard() {
      if (isAuthenticated) {
        this.$router.push('/dashboard')
      } else {
        this.$router.push('/login')
      }
    },
  },
}
```
### 3. Dynamic Route Matching with Params
```javascript
const User = {
  template: '<div>User</div>',
}

// these are passed to `createRouter`
const routes = [
  // dynamic segments start with a colon
  { path: '/users/:id', component: User },
]
```
. When a route is matched, the value of its params will be exposed as `this.$route.params`
```javascript
const User = {
  template: '<div>User {{ $route.params.id }}</div>',
}
```
### 4. Nested Routes

```javascript
const User = {
  template: '<div>User {{ $route.params.id }}</div>',
}

// these are passed to `createRouter`
const routes = [{ path: '/user/:id', component: User }]
// id: đường dẫn con trong use truyền thông qua $route.params.id
```
### 5. Programmatic Navigation
+ `router.push` để điều hướng đến một URL khác
```javascript
router.push(location, onComplete?, onAbort?)
```
+ `router.replace` điều hướng mà không cần đẩy một mục lịch sử mới,  nó thay thế mục nhập hiện tại.
```javaScript
router.replace(location, onComplete?, onAbort?)
```
+ `router.go(n)` nhận một số nguyên duy nhất làm tham số cho biết có bao nhiêu bước tiến hoặc lùi trong ngăn xếp lịch sử 
```javaScript
router.go(1)// tiến lên 1 trang
router.go(-100)// lùi 100 trang
```
+ `<router-link :to="...">`tương đương với việc gọi `router.push(...)`
```javascript
// literal string path
router.push('/users/eduardo')

// object with path
router.push({ path: '/users/eduardo' })

// named route with params to let the router build the url
router.push({ name: 'user', params: { username: 'eduardo' } })

// with query, resulting in /register?plan=private
router.push({ path: '/register', query: { plan: 'private' } })

// with hash, resulting in /about#team
router.push({ path: '/about', hash: '#team' })
```
```javascript
const username = 'eduardo'
// we can manually build the url but we will have to handle the encoding ourselves
router.push(`/user/${username}`) // -> /user/eduardo
// same as
router.push({ path: `/user/${username}` }) // -> /user/eduardo
// if possible use `name` and `params` to benefit from automatic URL encoding
router.push({ name: 'user', params: { username } }) // -> /user/eduardo
// `params` cannot be used alongside `path`
router.push({ path: '/user', params: { username } }) // -> /use
```
### 6. Redirect
+ Để chuyển hướng từ `/home` đến `/`:
```javascript
const routes = [{ path: '/home', redirect: '/' }]
  // redirect:đi đến 1 router không tồn tại từ thanh địa chỉ browser
const routes = [{ path: '/home', redirect: { name: 'homepage' } }]
 ```
+ Chuyển hướng tương đối
```javascript
const routes = [
  {
    // will always redirect /users/123/posts to /users/123/profile
    path: '/users/:id/posts',
    redirect: to => {
      // the function receives the target route as the argument
      // a relative location doesn't start with `/`
      // or { path: 'profile'}
      return 'profile'
    },
  },
]
```
### 7. Alias
+ khi `/home` nhưng alias đến  `/` thì URL vẫn còn là `/home` còn URL `/` sẽ chuyển thành `/home`
```javascript
const routes = [{ path: '/', component: Homepage, alias: '/home' }]
```
### 8. Passing Props to Route Components
thay thế
```javascript
const User = {
  template: '<div>User {{ $route.params.id }}</div>'
}
const routes = [{ path: '/user/:id', component: User }]
```
với
```javascript
const User = {
  // make sure to add a prop named exactly like the route param
  props: ['id'],
  template: '<div>User {{ id }}</div>'
}
const routes = [{ path: '/user/:id', component: User, props: true }]
```
+ Boolean mode: khi `props` là `true`, `route.params` sẽ đặt component props
+ Named views
```javascript
const routes = [
  {
    path: '/user/:id',
    components: { default: User, sidebar: Sidebar },
    props: { default: true, sidebar: false }
  }
]
```
+ Object mode
```javascript
const routes = [
  {
    path: '/promotion/from-newsletter',
    component: Promotion,
    props: { newsletterPopup: false }
  }
]
```
+ Function mode
```javascript
const routes = [
  {
    path: '/search',
    component: SearchUser,
    props: route => ({ query: route.query.q })
  }
]
```
### 9. hash mode, history mode
+ Vue Router có hai chế độ cho URL đó là ở dạng hash mode (mặc định) và history:

1. Hash Mode: mô phỏng URL ở dạng hash (#), để loại bỏ hash(#) thì dùng `mode: 'history'`
2. History: dạng rất quen thuộc khi đường dẫn tới các path bằng '/' Để thay đổi sang history mode ta chỉ cần thêm vào VueRouter:

```javascript
export const router = new VueRouter({
    mode: 'history',
    routes: [
        {path: '/', component: Home},
        {path: '/about', component: About}
    ]
})
```
### Question
1. Làm thế nào để điều huớng đến 1 router bất kỳ trong hệ thống.
+ ta dùng `router.push`(location, onComplete?, onAbort?)
2.Nếu đi đến 1 router không tồn tại từ thanh địa chỉ browser, thì mình xử lý như thế nào và xử lý ở đâu?
+ tại file chứa các path 
```javascript
{path:'/all-jobs', redirect:'/userGame'}
```
`redirect`: đi đến 1 router không tồn tại từ thanh địa chỉ browser

#### [Video tham khảo](https://www.youtube.com/watch?v=juocv4AtrHo)
---


## Vuex
### 1. Khái niệm: 
+ Vuex là thư viện giúp quản lý state của các component trong Vue.js, nó là nơi lưu trữ tập trung cho tất cả các component trong một ứng dụng, với nguyên tắc state chỉ có thể được thay đổi theo kiểu có thể dự đoán.
+ Vue hoạt động theo mô hình "Luồng dữ liệu một chiều" 
1. `State`: Trạng thái, là nơi khởi nguồn để thực hiện ứng dụng.
2. `View` là các khai báo ánh xạ với trạng thái.
3. `Action` là những cách thức làm trạng thái thay đổi phản ứng lại các nhập liệu của người dùng từ View

### 2. Cài đặt
npm
```sh
npm install vuex@next --save
```
yarn
```sh
yarn add vuex@next --save
```
### 3.  Store
+ `state` : nơi lưu trữ các trạng thái ứng dụng
```javascript
const state = {
  count: 0
}
////
export default {
    computed: {
        result() {
            return this.$store.state.result;
        }
    }
}
```
+ `getters` : là những hàm để lấy ra state, có helper là `mapGetters`
```javascript
const state = {
  getEvenNumbers: state => {
    return state.numbers.filter(item => item%2 === 0)
  }
  hasNumber : state => num => {
    return state.numbers.include(num)
  }
}
```

+ `mutations` :  những hàm để thay đổi state, helper là `mapMutations`, `commit` để gọi `mutations`
```javascript
// ...
mutations: {
  increment (state, payload) {
    state.count += payload.amount
  }
}
//
store.commit('increment', {
  amount: 10
})
//.....
```
+ `actions` : tương tự như mutation,Thay vì thay đổi trạng thái thì các action commit thay đổi `mutations`, nó có thể chứa các hoạt động không đồng bộ. có helper là `mapAction`,`store.dispatch`, `dispatch` để gọi `actions`

```javascript
//Composing Actions
actions: {
  actionA ({ commit }) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        commit('someMutation')
        resolve()
      }, 1000)
    })
  }
}
///
store.dispatch('actionA').then(() => {
  // ...
})
//
store.dispatch('actionA').then(() => {
  // ...
})

//action khac
actions: {
  // ...
  actionB ({ dispatch, commit }) {
    return dispatch('actionA').then(() => {
      commit('someOtherMutation')
    })
  }
}

///   dùng async / await, để xử lí các hành động
// assuming `getData()` and `getOtherData()` return Promises

actions: {
  async actionA ({ commit }) {
    commit('gotData', await getData())
  },
  async actionB ({ dispatch, commit }) {
    await dispatch('actionA') // wait for `actionA` to finish
    commit('gotOtherData', await getOtherData())
  }
}
```

+ Module: Vuex cho phép chia nhỏ store thành các module nhỏ hơn, mỗi module cũng có state, mutation, action, getter và thậm chí còn cho phép các module lồng nhau.


### Question
1. State management là gì? Tại sao lại cần sử dụng nó?
+ phương pháp để quản lý state trong ứng dụng
+ vì có thể chia sẻ dữ liệu giữa các component với nhau và cập nhập dữ liệu khi các component thay đổi
2. Lợi ích của việc sử dụng vuex trong dự án vuejs? 
+ Với những dự án sử dụng nhiều component hoặt động độc lập, phức tạp thì Vuex với nguyên tắc state có thể thay đổi theo kiểu dự đoán sẽ quản lí các state bằng việc sử dụng store toàn cục vì thế các component có thể chia sẻ, thay đổi dữ liệu 1 cách dễ dàng thông qua store toàn cục.

---
## Vuetify
#### 1. khái niệm: là 1 UI Framework hoàn chỉnh được xây dựng trên VueJs
#### 2. Cài đặt
```sh
vue add vuetify
```
Vue UI install
```sh
# Then start the UI
vue ui
```
Nuxt install
```sh
yarn add @nuxtjs/vuetify -D
# OR
npm install @nuxtjs/vuetify -D
```
Webpack install
```sh
yarn add vuetify
# OR
npm install vuetify
```
```sh
yarn add sass@~1.32 sass-loader deepmerge -D
# OR
npm install sass@~1.32 sass-loader deepmerge -D
```
#### 3. Import Vuetify
```javaScript
// src/main.js
import Vue from 'vue'
import App from './App.vue'
import vuetify from './plugins/vuetify';

Vue.config.productionTip = false

new Vue({
  vuetify,
  render: h => h(App)
}).$mount('#app')
```



