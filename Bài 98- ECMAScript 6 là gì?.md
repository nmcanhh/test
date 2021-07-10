## Bài 98: ECMAScript 6 là gì?

ES6 là ECMAScript phiên bản thứ 6, ra đời vào năm 2015. ES6 được chuẩn hóa bởi ECMA International, được tạo ra để chuẩn hóa Javascript.

---

## Bài 99: Let & Const

`let`, `const` sinh ra với mục đích thay thế từ khóa `var` để khai báo cho các biến.

### 1. Phạm vi truy cập (scope)

Chúng ta ví dụ với các Code block: `If-else`, `loop`, `{}`, ...

	if (true) {
	  var course = "Javascript basic!";
	}

có thể viết thành 

	{
	  var course = "Javascript basic!";
	}

### 1.1. Giống nhau

cả 3 đều sử dụng khai báo biến

### 1.2. Khác nhau

a) `var` khai báo biến trong code block, khi **ra ngoài dùng lại biến này thì vẫn được.**

	{
	  var course = "Javascript basic!";
	}
	
	console.log(course);


b) `let`, `const` khai báo biến trong code block, khi **ra ngoài dùng lại biến này thì không được.**

Biến được khai báo bằng `let`, `const` chỉ có giá trị sử dụng trong code block, ví dụ:

	{
	  const course = 'Javascript basic!';
	
	  {
	    {
	      console.log(course);
	    }
	  }
	}

Vì ở đây `course` được khai báo ở code block cha, còn `console.log(course)` được khai báo ở code block con.

c) Biến được khai báo bằng `let`, `const` ở trong code block con thì không ảnh hưởng đến biến đã được khai báo trước đó ở các code block cha. Có thể nói là nó sẽ ưu tiên biến được khai báo ở block gần nhất, và không báo trùng tên biến.

	{
	  const course = 'Javascript basic!';
	
	  {
	    {
	      const course = '123';
	      console.log(course);
	    }
	  }
	}

Ở đây, chương trình sẽ in ra là `123` chứ không in ra `Javascript basic!`, mặc dù `course` đã được khai báo code block cha trước đó, tuy nhiên khi ta khai báo course bằng `let`, `const` ở code block con vẫn không ảnh hưởng gì. 

d) Hoisting (đưa khai báo biến lên đầu)

Chúng ta có thể gán giá trị biến trước khi khai báo biến, ví dụ:

	a = 1;
	var a;
	console.log(a);

Trình thông dịch sẽ tự hiểu và đưa khai báo biến `var a;` lên đầu, vậy nên trong trường hợp **gán giá trị trước khai báo biến thì vẫn không xảy ra lỗi**

Với `let`, `const` thì không được hỗ trợ hoisting.

e) Gán giá trị cho biến (Assignment)

Chúng ta có thể gán giá trị cho 1 biến đến lần thứ 2 với `var` và `let`

	var a = 1;
	
	a = 2;
	
	console.log(a)

hoặc

	let a = 1;
	
	a = 2;
	
	console.log(a)

Kết quả:

	2
	
Tuy nhiên chúng ta không thể sử dụng với `const`


	const a = 1;
	
	a = 2;
	
	console.log(a)

Lưu ý 1 trường hợp dễ bị lừa:

	const a = {
	  name: 'Javascript',
	};
	
	a.name = `PHP`;
	
	console.log(a.name);
	
Ở đây chúng ta có thể gán thuộc tính `name` tới lần 2, nhưng đây là gán thuộc tính chứ không phải gán biến, nếu gán biến `a` lại lần 2 thì vẫn lỗi như thường.

Tóm lại:

Kiểu khai báo| Dùng ngoài Block| Không dùng ngoài Block| Hoisting| Không Hoisting| Gán lại| Không gán lại|          
-------------|-----------------|-----------------------|---------|---------------|--------|--------------|
`var`|x| |x| |x||
`let`||x||x|x||
`const`||x||x| |x|

Trường hợp sử dụng:

Code thuần, không sử dụng bất kỳ thư viện nào: `var`

Babel: `let`, `const`

Trường hợp sử dụng `let`, `const`

Khi không cần gán lại biến: `const`

Khi cần gán lại giá trị cho biến: `let`

---

## Bài 100: Template literals (Template String)


### 1. Template literals

a) Cộng chuỗi

	const courseName = 'Javascript';
	const description = 'Course name:' + courseName;
	console.log(description);

Kết quả:

![](https://i.ibb.co/2t02kWs/Screen-Shot-2021-07-09-at-16-12-14.png)

b) Multi-line String

	const lines = 'Line 1\n'
	      + 'Line 2\n'
	      + 'Line 3\n'
	      + 'Line 4\n';
	console.log(lines);
	
Kết quả:
	
![](https://i.ibb.co/nLW9CRY/Screen-Shot-2021-07-09-at-16-09-23.png)

### 2. Template string

a) Cộng chuỗi

	const car1 = 'Lamborghini';
	const car2 = 'Vinfast';
	const total = `Các loại xe: ${car1}, ${car2}, ...`;
	console.log(total);

Kết quả:

![](https://i.ibb.co/8gF1bYr/Screen-Shot-2021-07-09-at-16-11-08.png)

b) Multi-line String

	const lines = `Line 1
	Line 2
	Line 3
	Line 4`;
	console.log(lines);

Kết quả:
	
![](https://i.ibb.co/nLW9CRY/Screen-Shot-2021-07-09-at-16-09-23.png)

---

## Bài 101: Arrow function
 
### 1. Declaration Function

Ví dụ:

	function logger(log){
	  console.log(log);
	}
	logger('Message...');

### 2. Expression Function

Ví dụ:

	const logger = function(log){
	  console.log(log);
	}
	logger('Message...');

### 3. Arrow function

Ví dụ 1:

	const logger = (log) => {
	  console.log(log);
	}

Ví dụ 2:

	const sum =  (a,b) => {
	  return a + b;
	}
	console.log(sum(2,2));

Với Arrow function chỉ có return thì chúng ta có thể sử dụng các viết dưới đây:

	const sum =  (a,b) => a + b;
	
	console.log(sum(2,2));

Phía sau dấu `=>` sẽ được hiểu là return

Khi chúng ta sử dụng cặp `{}` sau dấu `=>` thì nó sẽ không return, mà sẽ được hiểu là khối code mà chúng ta phải sử dụng từ khóa return.

Ví dụ 3: Return về 1 object

	const sum = (a,b) => {
	  return {
	    a: a,
	    b: b
	  };
	};
	
	console.log(sum(2,2));

hoặc 

	const sum = (a,b) => ({a: a, b: b});
	
	console.log(sum(2,2));	

Ví dụ 4: 

Với những function chỉ có duy nhất 1 tham số truyền vào như dưới đây:

	const logger = (log) => console.log(log);
	
	logger('Message...')

Thì chúng ta có thể bỏ đi cặp ngoặc đơn ở tham số như sau:

	const logger = log => console.log(log);
	
	logger('Message...')
	
Ví dụ 5:

	const course = {
	  name: 'Javascript basic!',
	  getName: function(){
	     return this.name;
	  }
	}
	
	console.log(course.getName());
	
`this` ở đây là `course` và được gọi là context. Trong Arrow function thì chúng ta không sử dụng được context.

Ví dụ 6:

Arrow function không thể sử dụng để làm object constructor.

	const Course = function(name, price) {
	  this.name = name;
	  this.price = price;
	}
	
	const jsCourse = new Course('Javascript', '1000');
	
	console.log(jsCourse);

Nếu đổi thành Arrow function thì sẽ sinh ra lỗi.

## Bài 102: Classes

Bình thường chúng ta viết Object Constructor như dưới đây:

	function Course(name, price) {
	  this.name = name;
	  this.price = price;
	}
	
	const phpCourse = new Course('PHP', 1000);
	const jsCourse = new Course('Javascript', 1000);
	
	console.log(phpCourse);
	console.log(jsCourse);

Bây giờ, chúng ta có thể viết thành `class`:

	class Course {
	    constructor(name, price){
	      this.name = name;
	      this.price = price;
	    }
	}
	
	const phpCourse = new Course('PHP', 1000);
		const jsCourse = new Course('Javascript', 1000);
	
	console.log(phpCourse);
	console.log(jsCourse);

### Sự tiện lợi của `class`

Với Object Constructor, chúng ta viết thuộc tính, phương thức, biến đều chung 1 cấp 

	function Course(name, price) {
	  this.name = name;
	  this.price = price;
	  this.getName = function(){
	  		return this.name;
	  	}
	}

Với Class, chúng ta viết thuộc tính, phương thức khác cấp với nhau

	class Course {
	    constructor(name, price){
	      this.name = name;
	      this.price = price;
	    }
	    getName() {
	      return this.name;
	    }
	    getPrice() {
	      return this.price;
	    }
	}

---

## Bài 103: Default parameter values - định nghĩa giá trị mặc định cho tham số

Khi định nghĩa hàm, chúng ta biết có những tham số không bắt buộc phải nhập thì chúng ta đặt những tham số này nằm ở giá trị mặc định.

	function logger(log = '0'){
	  console.log(log);
	}
	
	logger();

Chúng ta vẫn có thể nhập giá trị vào `logger()` là `logger(123)` thì vẫn in ra là `123`. Nhưng nếu không nhập gì thì mặc định sẽ in ra là `0`

Ví dụ:

	function logger(log, type = "log") {
	  console[type](log);
	}
	
	logger("Message...");
	
---

## Bài 104: Enhanced object literals

### 1. Định nghĩa key: value cho object

Thuộc tính trong object phải giống với tên biến đã được khai báo
	
### 2. Định nghĩa phương thức cho 1 objects

Thay vì `getName: function(){}`, chúng ta viết thành `getName(){}`


![](https://i.ibb.co/kmHDBsK/New-Project-2.png)

### 3. Định nghĩa key cho object dưới dạng biến (ít dùng)

	var fieldName = 'name';
	var fieldPrice = 'price';
	
	const course = {
	  [fieldName]: 'Javascript',
	  [fieldPrice]: 1000
	};
	
	console.log(course);

---

## Bài 105: Destructuring - Phân rã

### 1. Array

a) Cách viết thông thường

	var array = ['JavaScript', 'PHP', 'Rubby'];
	
	var a = array[0];
	var b = array[1];
	var c = array[2];
	
	console.log(a, b, c);
	
Kết quả:

![](https://i.ibb.co/wST1HQ4/Screen-Shot-2021-07-10-at-10-20-11.png)

b) Sử dụng Destructuring, chúng ta gán `a`, `b`, `c` cho các phần tử trong mảng lần lượt là `JavaScript `, `PHP `, `Rubby `.

	var array = ['JavaScript', 'PHP', 'Rubby'];
	
	var [a, b, c] = array;
	
	console.log(a, b, c);

Kết quả:

![](https://i.ibb.co/wST1HQ4/Screen-Shot-2021-07-10-at-10-20-11.png)
	
c) Nếu chỉ lấy ra `a` và `c` thì chúng ta xóa đi `b` ở phần gán mảng biến mà vẫn để lại dấu phẩy

	var array = ['JavaScript', 'PHP', 'Rubby'];
		
	var [a, , c] = array;
	
	console.log(a, c);

Kết quả:

![](https://i.ibb.co/HKMXvzZ/Screen-Shot-2021-07-10-at-10-21-38.png)
	
d) Rest Parameters - lấy ra những phần còn lại

Ban đầu, chúng ta lấy ra `a`, sau đó chúng ta sử dụng `...rest`. Lúc này, `rest` sẽ được gán cho 2 phần tử còn lại của mảng. 

Chú ý: `rest` có thể được đặt tên tùy ý.

	var array = ["JavaScript", "PHP", "Rubby"];
	
	var [a, ...rest] = array;
	
	console.log(a); // string
	console.log(rest); // array

Kết quả:

![](https://i.ibb.co/82mwnnS/Screen-Shot-2021-07-10-at-10-22-29.png)

### 2. Object

a) Sử dụng Destructuring, chúng ta gán các biến cho các key trong object lần lượt là `name `, `price`, `image `. 

Chú ý: tên biến phải giống với tên key. 

	var course = {
	    name: 'Javascript',
	    price: 1000,
	    image: 'image-address'
	};
	
	var { name, price, image} = course;
	
	console.log(name, price, image);

Kết quả:

![](https://i.ibb.co/pr1cjCz/Screen-Shot-2021-07-10-at-10-23-25.png)

b) Nếu chỉ lấy ra `name` và `price` thì chúng chỉ cần gọi các biến trùng trên với key ra.

	var course = {
	    name: 'Javascript',
	    price: 1000,
	    image: 'image-address'
	};
	
	var { name, image} = course;
	
	console.log(name, image);
	
Kết quả:

![](https://i.ibb.co/wQphzBk/Screen-Shot-2021-07-10-at-10-24-45.png)

c) Rest Parameters - lấy ra những phần còn lại

	var course = {
	  name: 'Javascript',
	  price: 1000,
	  image: 'image-address'
	};
	
	var { name, ...rest} = course;
	
	console.log(name);
	console.log(rest);

Kết quả:

![](https://i.ibb.co/HhXKhS1/Screen-Shot-2021-07-10-at-10-26-33.png)


Lúc này, `rest` là 1 object mới không chứa key `name`. Đây cũng là mẹo để xóa đi 1 key của object.

d) Đổi tên biến 

Chúng ta thêm dấu `:` và tên biến mới vào sau tên biến cũ

	var course = {
	  name: 'Javascript',
	  price: 1000,
	  image: 'image-address'
	};
	
	var { name: newName, price: newPrice } = course;
	
	console.log(newName, newPrice );

Kết quả:
	
![](https://i.ibb.co/Dw1jwCL/Screen-Shot-2021-07-10-at-10-27-21.png)
	
e) Object có object con

Ở phần biến, chúng ta gọi biến ra bằng cách gọi `children: {tên biến}`, nếu tên biến trùng với tên biến trước đó thì chúng ta đổi tên biến đó đi.

	var course = {
	  name: 'Javascript',
	  price: 1000,
	  image: 'image-address',
	  children: {
	      name: 'ReactJS'
	  }
	};
	
	var {name, children: { name: newName }} = course;
	
	console.log( name, newName );
	
Kết quả:

![](https://i.ibb.co/Qm6VF63/Screen-Shot-2021-07-10-at-10-28-01.png)

f) Giá trị mặc định của biến

Khi biến gọi ra key không có trong object thì chúng ta đặt giá trị mặc định cho nó.

	var course = {
	  name: 'Javascript',
	  price: 1000,
	  image: 'image-address',
	};
	
	var {name, description = 'default description'} = course;
	
	console.log(name);
	console.log(description); 
	
Kết quả:

![](https://i.ibb.co/hdKVnGb/Screen-Shot-2021-07-10-at-10-28-43.png)

Ngược lại, khi biến gọi ra key đã có trong object thì biến sẽ lấy giá trị của key đó trong object

	var course = {
	  name: 'Javascript',
	  price: 1000,
	  image: 'image-address',
	  description: 'description value'
	};
	
	var {name, description = 'default description'} = course;
	
	console.log(name);
	console.log(description);	
	
Kết quả:

![](https://i.ibb.co/jV7j2nv/Screen-Shot-2021-07-10-at-10-29-46.png)

g) Rest Parameters trong Function

☯ Bình thường, chúng ta tạo 1 function với chức năng là in ra các giá trị truyền vào như sau:

	function logger(params) {
	  console.log(params);
	}
	
	logger(1,2,3,4,5,6,7,8);

Kết quả:

![](https://i.ibb.co/8dpBzXc/Screen-Shot-2021-07-10-at-14-50-41.png)

Dù có truyền vào bao nhiêu thì kết quả nhận được cũng chỉ là `1`


☯ Khi sử dụng toán tử `rest` trong tham số thì chúng ta in ra 1 array có số phần tử bằng số phần tử truyền vào. Vì sau toán tử `rest` thì toàn bộ các giá trị còn lại đều được gán cho biến `params` nên hiển nhiên khi truyền vào vào nhiêu thì biến `params` sẽ nhận lại bấy nhiêu. 

	function logger(...params) {
	    console.log(params);
	}
	
	logger(1,2,3,4,5,6,7,8);
	
Kết quả:

![](https://i.ibb.co/R3HSvnT/Screen-Shot-2021-07-10-at-10-30-26.png)

☯ Khi chúng ta sử dụng destructuring

✶ Truyền vào 1 dãy số: 

	function logger(a, b, ...params) {
	  console.log(a, b);
	  console.log(params);
	}
	
	logger(1,2,3,4,5,6,7,8);

Kết quả: 

![](https://i.ibb.co/3s12Dvr/Screen-Shot-2021-07-10-at-14-57-16.png)

Lúc này, `a` sẽ được gán cho giá trị truyền vào đầu tiên và `b` sẽ được gán cho giá trị truyền vào thứ 2, các giá trị còn lại đều là của `params` hết.

✶ Truyền vào 1 object:

	function logger({ name, price, ...rest}) {
	  console.log(name); //string
	  console.log(price); //string
	  console.log(rest); //object
	}
	
	logger({
	  name: 'Javascript',
	  price: 1000,
	  description: 'Description content' 
	});

Kết quả:

![](https://i.ibb.co/3SzKtzv/Screen-Shot-2021-07-10-at-15-04-30.png)

Lúc này, `name` sẽ được gán cho key `name` của object truyền vào và `price` sẽ được gán cho key `price ` của object truyền vào, các key còn lại đều là của `rest` hết.

✶ Truyền vào 1 array:

	function logger([a, b, ...rest]) {
	  console.log(a);
	  console.log(b);
	  console.log(rest);
	}
	
	logger([2, 4, 6, 8, 10, 12]);

Kết quả:

![](https://i.ibb.co/PxCs0mL/Screen-Shot-2021-07-10-at-15-08-03.png)

Lúc này, `a` sẽ được gán cho phần tử đầu tiên của mảng truyền vào và `b` sẽ được gán cho phần tử thứ 2 của mảng truyền vào, các phần tử còn lại đều là của `params` hết.

---

## Bài 106: Spread - toán tử giải

Khi sử dụng `spread` `...` trước array hoặc object thì nó sẽ bỏ đi cặp dấu ngoặc `[]` hoặc `{}`

### 1. Nối mảng

Bài toán: Nối mảng `array1` và `array2` thành `array3`

	var array1 = ['Javascript', 'Rubby', 'PHP'];
	
	var array2 = ['ReactJS', 'Dart'];
	
	var array3 = [...array1, ...array2];
	
	console.log(array3);

Kết quả: 

![](https://i.ibb.co/hfpfwD5/Screen-Shot-2021-07-10-at-15-19-59.png)

Chúng ta vẫn có thể sử dụng `concat`

### 2. Nối object

Bài toán: Nối `object1` và `object2` thành `object3`

	var object1 = {
	  name: 'Javascript'
	};
	
	var object2 = {
	  price: 1000
	};
	
	var object3 = {
	  ...object1,
	  ...object2
	};
	
	console.log(object3);
	
Kết quả:

![](https://i.ibb.co/p4tDMFd/Screen-Shot-2021-07-10-at-15-25-30.png)

## 3. Sử dụng cả Spread và Rest

	var array = ['Javascript', 'PHP', 'Ruby'];
	
	function logger(...rest){ // này là rest
	    for (var i = 0; i < rest.length; i++){
	      console.log(rest[i]);
	    }
	}
	
	logger(...array); // này là spread
	
Kết quả:

![](https://i.ibb.co/1G2hsnp/Screen-Shot-2021-07-10-at-15-56-14.png)


---

## Bài 107: Tagged template literals

---

## Bài 108: Modules

### Ví dụ 1:

✶ Tại file `index.html`

	<script type="module" src="./app.js"></script>

✶ Tại file module `logger.js`, sử dụng `export default tên_module` 

	function logger(log, type = 'log') {
	  console[type](log);
	}
	
	export default logger;

✶ Tại file `app.js`, sử dụng `import tên_module from đường_dẫn`

	import logger from './logger.js';
	
	logger('Test message...'); // sử dụng function đã định nghĩa trong module
	
✶ Kết quả:

![](https://i.ibb.co/Rjtw2kH/Screen-Shot-2021-07-10-at-21-33-44.png)

### Ví dụ 2:

✶ Tại file `index.html`

	<script type="module" src="./app.js"></script>

✶ Tại file module `logger.js`, chúng ta có thể sử dụng `export` bình thường nhiều lần nhưng chỉ `export default` duy nhất 1 lần.

	export const TYPE_LOG = 'log';
	export const TYPE_WARN = 'warn';
	export const TYPE_ERROR = 'error';
	
	function logger(log, type = TYPE_LOG) {
	  console[type](log);
	}
	
	export default logger;

✶ Tại file `app.js`, thêm `{ TYPE_LOG, TYPE_WARN, TYPE_ERROR }` vào sau module để Destructuring để sử dụng các biến này.

	import logger, {
	  TYPE_LOG,
	  TYPE_WARN,
	  TYPE_ERROR
	} from './logger.js';
	
	logger('Test message...', TYPE_LOG);
	logger('Test message...', TYPE_WARN);
	logger('Test message...', TYPE_ERROR);

✶ Kết quả:

![](https://i.ibb.co/2NQyXx7/Screen-Shot-2021-07-10-at-21-45-07.png)

### Ví dụ 3:

✶ Cấu trúc thư mục:

![](https://i.ibb.co/Nr9TJBP/Screen-Shot-2021-07-10-at-22-26-31.png)

✶ Tại file `index.html`

	<script type="module" src="./app.js"></script>

✶ Tại file module `logger.js`
	
	function logger(log, type = TYPE_LOG) {
	  console[type](log);
	}
	
	export default logger;

✶ Tạo thêm 1 file module chứa các constant có tên là `constants.js`

	export const TYPE_LOG = 'log';
	export const TYPE_WARN = 'warn';
	export const TYPE_ERROR = 'error';

✶ Tại file `app.js`, `import { TYPE_LOG, TYPE_WARN, TYPE_ERROR } from './constants.js'`

	import logger from './logger.js';
	import {
	  TYPE_LOG,
	  TYPE_WARN,
	  TYPE_ERROR
	} from './constants.js';
	
	logger('Test message...', TYPE_LOG);
	logger('Test message...', TYPE_WARN);
	logger('Test message...', TYPE_ERROR);

hoặc tại file `app.js`, `import * as constants from './constants.js'`

	import logger from './logger.js';
	
	import * as constants from './constants.js';
	
	logger('Test message...', constants.TYPE_LOG);
	logger('Test message...', constants.TYPE_WARN);
	logger('Test message...', constants.TYPE_ERROR);
	
✶ Kết quả:

![](https://i.ibb.co/2NQyXx7/Screen-Shot-2021-07-10-at-21-45-07.png)

### Ví dụ 4:

✶ Cấu trúc thư mục:

![](https://i.ibb.co/Zx7zHz2/Screen-Shot-2021-07-10-at-22-30-28.png)

✶ Tại file `index.html`

	<script type="module" src="./app.js"></script>

✶ Tạo file trung gian là `logger/index.js`, chúng ta khai báo

	import logger from './logger.js';

	export default logger;
	
hoặc

	export { default } from './logger.js';

hoặc tạo 1 tên mới 

	export { default as logger2 } from './logger.js';


✶ Tại file `logger/logger.js`, ta thêm 1 dấu chấm `.` vì hiện tại `logger.js` thua 1 cấp so với `constants.js`

	import { TYPE_LOG } from '../constants.js';
	
	function logger(log, type = TYPE_LOG) {
	  console[type](log);
	}
	
	export default logger;
	
✶ Tại file `app.js` ta khai báo thêm `import logger from './logger/index.js'`

	import logger from '../logger/index.js';
	import * as constants from './constants.js';
	
	logger('Test message...', constants.TYPE_LOG);
	logger('Test message...', constants.TYPE_WARN);
	logger('Test message...', constants.TYPE_ERROR);

✶ Kết quả:

![](https://i.ibb.co/2NQyXx7/Screen-Shot-2021-07-10-at-21-45-07.png)
