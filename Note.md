## Bài 3, 4: Cách sử dụng JS với HTML
### Có 2 cách thông dụng:

### 1. Internal (nội bộ)

```
<body>
    ...
    <script>
        alert('Xin chào các bạn!');
    </script>
    ...
</body>

```
### 2. External (file .js bên ngoài)

```
<body>
    ...
    <script src="đường_dẫn_tới_file.js"></script>
</body>
```
Trong file .js có dạng

```
alert('Xin chào các bạn!');
```
---
## Bài 5: Biến và khai báo biến
### Lưu ý:

1. Tên biến có thể bao gồm chữ cái, số, dấu gạch dưới ( _ ) và kí tự đô la ( $ )

	 	Ví dụ: họVàTên, $$$$, $address, vi2en, _this, fullName, $_$, ດ້ານວິຊາການ
	
2. Tên biến không thể bắt đầu bằng số, phải bắt đầu bằng một chữ cái hoặc dấu gạch dưới hoặc dấu đô la.
3. Tên biến phân biệt chữ hoa và chữ thường. Vì vậy tenbien và TenBien là 2 biến khác nhau.
4. Tên biến không được (không thể) đặt trùng với các từ khóa của Javascript 

---


## Bài 11: Một số hàm Built-in
**Built-in function** nghĩa là hàm cài sẵn, chức năng lập sẵn. Hiểu đơn giản là những hàm được tích hợp sẵn trong ngôn ngữ lập trình.

**Ví dụ 1:**

	console.log(), console.warn(), console.error()

Những hàm này đều truyền biến hoặc 1 chuỗi vào là chạy.

**Ví dụ 2:**

	alert(), confirm(), prompt()

Những hàm này khi chạy sẽ hiển thị dialog trên trình duyệt.

**Ví dụ 3:**

Hàm Set Timeout - thực thi 1 function sau bao nhiêu lâu

	setTimeout(function(){
	 alert('Thông báo');
	}, 5000)

**Ví dụ 4:**

Hàm Set Interval - Thực thi 1 function sau 1 thời gian định kỳ

	setInterval(function() {
	    console.log('Đây là log' + Math.random())
	}, 3000)
---

## Bài 12: Làm quen với toán tử

### Toán tử số học
	var a = 1 * 2;
	console.log(a);
	
### Toán tử gán
	var fullName = 'Dang Ngoc Son';


### Toán tử so sánh
	var a = 1;
	var b = 2;
	
	if (a < b) {
	    alert('Đúng!');
	}

### Toán tử logic
	var a = 1;
	var b = 2;
	
	if (a > 0 && b > 0){
	    alert('a & b lớn hơn 0')
	}

### Bài tập cần chú ý
	var a = '15' - 5;
Kết quả là 10

---

## Bài 14: Toán tử số học

### Bài tập cần chú ý
	var a = 5 + '5'
Kết quả là ‘55’

---

## Bài 15: Toán tử (++/--) tiền tố và hậu tố

	var a = 6;

### Trường hợp ++a
	Việc 1: + 1 cho a, a = a + 1 => a = 7 
	
	Việc 2: Trả về a sau khi được + 1


### Trường hợp a++

	Việc 1: 'a copy', 'a copy' = 6
	
	Việc 2: cộng 1 của a, a = a + 1 => a = 7
	
	Việc 3: trả về 'a copy'

### Ví dụ: 
	var output = number++ + --number;
	console.log(output);

**Giải thích:**

number ban đầu = 6, sau đó number++ thì lấy giá trị 6. Tới lần thứ 2 sử dụng number thì mới lấy giá trị 7. Tới --number thì thành --7 = 6. Kết quả = 12.

---

## Bài 16: Toán tử gán

Toán tử        		| Ví dụ            	| Tương đương           |
--------------------|------------------	|-----------------------|
=						|x = y            	|x = y                  |
+=         	      	|x += y      	   		|x = x + y              |
-=         	      	|x -= y      	   		|x = x – y              |
*=						|x *= y      			|x = x * y              |
/=						|x /= y      			|x = x / y              |
**=						|x **= y     			|x = x ** y             |

### Ví dụ:

	var a = 1;
	a += 2; // a = a + 2
	

---
	
## Bài 17: Toán tử chuỗi

### Ví dụ 1:
	var firstName = 'Son';
	var lastName = 'Dang';
	console.log(firstName + ' ' + lastName);
### Ví dụ 2:
	var name = "Son";
	name += " Dang";
	console.log(name);
### Ví dụ 3:  
	var result = 1 + 2 + '3'
Ở đây 1 + 2 = 3 trước, sau đó 3 sẽ nối chuỗi với ‘3’ thành 33

### Ví dụ 4: 
	var result = '3' + 2 + 1
Ở đây 3 nối chuỗi với 2 thành 32, sau đó 32 nối chuỗi với 1 thành 321

---

## Bài 18: Toán tử so sánh

Toán tử        		| Ý nghĩa          	|
--------------------|------------------	|
==						|Bằng					|
!=              		|Không bằng			|
\>               	|Lớn hơn				|
<						|Nhỏ hơn				|
\>=						|Lớn hơn hoặc bằng	|
<=						|Nhỏ hơn hoặc bằng	|

	var a = 1;
	var b = 2;
	
	if (a < b) {
	    console.log('Điều kiện đúng');
	} else {
	    console.log('Điều kiện sai');
	}
	
---

## Bài 19: Kiểu dữ liệu Boolean

	var a = 1;
	var b = 2;
	var isSuccess = a < b;
	console.log(isSuccess);
	
---

## Bài 20: Câu điều kiện If	
### Lưu ý: 6 giá trị dưới đây khi đưa vào if() đều là false, ngoài 6 giá trị dưới đây đều là true
	0
	false
	'' - ""
	undefined
	Nan
	null

### Ví dụ:

	var fullName = NaN;
	
	if (fullName) {
	    console.log('Điều kiện đúng');
	} else {
	    console.log('Điều kiện sai');
	}
	
---

## Bài 21: Toán tử Logical


Toán tử        		| Ý nghĩa          	|
--------------------|------------------	|
&&						| And: tất cả các điều kiện đều phải đúng thì đúng
l l						| Or: một trong các điều kiện đúng thì đúng
! 						| Not: phủ định của 1 điều kiện

### Ví dụ:
	var a = 1; 
	var b = 2;
	var c = 3;
	
	if (!(a < 0)){
	    console.log('Điều kiện đúng!');
	}

---

## Bài 22: Kiểu dữ liệu

### 1. Dữ liệu nguyên thủy
Dữ liệu nguyên thủy là đã tạo ra giá trị thì không sửa được trong vùng nhớ, phải gán giá trị mới để tạo ra vùng nhớ mới chứ không sửa được dữ liệu đã tạo trong vùng nhớ.

Gồm: `Number`, `String`, `Boolen`, `Undefined`, `Null`, `Symbol`

a) Number

	var a = 1;
	var b = 2;
	var c = 1.5;
	
b) String

	var fullName = 'Son Dang';
	
Lưu ý: Muốn để dấu nháy đơn trong chuỗi thì để bên ngoài là " "

c) Boolean

	var isSuccess = true;
	
d) Undefined (khi không khai báo giá trị biến)

	var age;
	console.log(age);
	
e) Null

	var isNull = null; //nothing
	console.log(typeof null); //typeof null là object
	console.log(isNull);

f) Symbol

	var id = Symbol('id'); //unique
	var id2 = Symbol('id'); //unique
	console.log(id == id2); //Không giống nhau vì unique

### 2. Dữ liệu phức tạp
Gồm: `Function`, `Object`

a) Function

	var myFunction = function(){
	    alert('Hiiii');
	}
	
Hàm sẽ chạy khi được gọi bằng cách:

	myFunction();
	
b) Object

	var myObject = {
	  name: "Son Dang", // 1 cặp key và value
	  age: 18,
	  address: "Ha Noi",
	  myFunction: function () {}, // có thể để được function
	};
	console.log('myObject', myObject);

Show danh sách thì dùng Array, vì Array không cần khai báo key

	var myArray = ["Javascript", "PHP", "Ruby"];
	console.log(myArray);

---

## Bài 23: Toán tử so sánh (2)

	=== bằng tuyệt đối
	!== khác tuyệt đối

### Ví dụ:

	var a = 1;
	var b = '1';
	console.log(a === b);

Khi dùng ==, nó chỉ quan tâm tới giá trị của 2 biến. Ví dụ 1 và '1' nó chỉ quan tâm tới giá trị 1 mà không cần biết đó là chuỗi hay số rồi cho ra kết quả là true. Nhưng dùng === thì nó sẽ so sánh chính xác hơn. Tương tự với !==

---

## Bài 24: Truthy và Falsy là gì?

--- 
## Bài 25: Toán tử Logical và câu lệnh điều kiện If?
### 1. Toán tử && (and)
### Ví dụ 1:

	var a = 1;
	var b = 2;
	var result = a < b && a > 0;
	console.log('result', result);

Ở đây kết quả sẽ cho ra là true.
Nhưng nếu chúng ta đổi result thành dưới đây:

	var result = a < b && a < 0;
	
Thì kết quả cho ra sẽ là false. Kết quả này là kết quả kiểm tra ở điều kiện a < 0.

Nguyên lý của toán tử && là khi nó check từ trái sang phải, nó check thấy cái nào sai thì nó sẽ báo ngay là false, còn nếu cứ check vào không thấy sai thì nó sẽ lấy kết quả cuối cùng làm kết quả được in ra. Kết quả cuối cùng này có thể là true hay false đều được. 

### Ví dụ 2:

	var result = 'A' && 'B' && 'C';
	console.log('result', result);

Ở đây kết quả trả về là C. Khi sử dụng toán tử &&, luôn đọc từ vế trái sang phải, vì những giá trị trên đều cho ra true nên mặc định nó sẽ đọc đến cuối dòng và lấy ‘C’ làm kết quả của result. Nhưng nếu B là 1 trong 6 giá trị Falsy thì sẽ lấy giá trị B gán cho result rồi in ra luôn mà không cần chạy sang C.

### Ví dụ 3:
	
	var result = 'A' && 'B' && NaN && 'D';
	if (result) {
	    console.log('Điều kiện đúng');
	} else {
	    console.log('Điều kiện sai ');
	}

Ở đây NaN là giá trị Falsy, vậy nên result sẽ được gán bằng giá trị của NaN (là false). Khi đưa vào If() thì nó sẽ chạy vào method false là console.log('Điều kiện sai')
Với những ví dụ trên, ta hiểu rằng khi đầu vào không thỏa mãn 1 điều kiện của câu điều kiện chứa toán tử && thì kết quả cho ra là false.

***“Câu lệnh này phải thỏa mãn A và B, câu lệnh không thỏa mãn A thôi thì là không thỏa mãn hết luôn rồi.”***
	
### 2. Toán tử || (or)
### Ví dụ 1:

	var result = "A" || "B" || "C" || "D";
	console.log("result", result);
	
Chỉ cần giá trị nào trả về bằng true thì sẽ lấy giá trị đó gán cho result. Ở đây ngay đầu tiên là ‘A’ mang giá trị true nên sẽ gán A làm giá trị của result.
### Ví dụ 2:

	var result = 'null' || 'B' || 'C' || 'D';

Lấy ‘B’ làm giá trị của result.

### Ví dụ 3:

	result = 'A' || 'B' || 'undefinded' || 'D';
Lấy ‘A’ làm giá trị của result.
Ở các trường hợp trên, null hay undefinded đều thuộc Falsy nên mang giá trị là false.

---

## Bài 26: Chuỗi

### 1. Các cách tạo chuỗi
### Cách 1:
	var fullName = 'Son Dang';
### Cách 2:
	var fullName = new String ('Son Dang');
	console.log(typeof fullName);

### 2. Một số trường hợp sử dụng backslash (\)
a) Backslash trước dấu nháy kép để in ra chuỗi chứ cặp nháy kép:

	var fullName = "Son Dang la \"Sieu Nhan\"";


b) Dấu backslash trước 1 dấu backslash để in ra chuỗi chứa dấu backslash:

	var fullName = 'Day la \\';

c) Backslash trước dấu nháy đơn để in ra chuỗi có dấu nháy đơn, trong trường hợp sử dụng cặp nháy đơn bao quanh chuỗi:

	var fullName = 'Son Dang la \'Sieu Nhan\'';

### 3. Cách xem độ dài chuỗi
	var fullName = 'Son Dang';
	console.log(fullName.length);

### 4. Chú ý độ dài khi viết code 
	var fullName = "Một số case sử dụng backslash"
	+ "Một số case sử dụng backslash"
	+ "Một số case sử dụng backslash"
	+ "Một số case sử dụng backslash";
	console.log(fullName);

### 5. Template String ES6 – Nối 2 biến với nhau mà không cần ghi dấu +
	var firstName = "Son";
	var lastName = "Dang";
	console.log(`Toi la: ${firstName} ${lastName}`);

---

## Bài 27: Làm việc với chuỗi
### 1. Độ dài của 1 chuỗi (Length)
	var myString = 'Hoc JS JS JS tai F8!';
	console.log('Độ dài của chuỗi là: ',myString.length);

### 2. Vị trí của ký tự trong chuỗi (Find Index)

### Ví dụ 1:
	console.log('Vị trí của ký tự là: ', myString.indexOf('JS'));

- Trả về -1 nếu không xuất hiện ký tự đó trong chuỗi
- Đếm ký tự từ 0
- Nếu trong chuỗi có 2 ký tự giống nhau, nó sẽ trả về vị trí xuất hiện đầu tiên của ký tự trong chuỗi

### Ví dụ 2:


	console.log('Vị trí của ký tự là: ', myString.indexOf('JS, 6'));
	
Có thể truyền vị trí bắt đầu đếm cho nó
Nếu trong chuỗi có nhiều ký tự JS, vị trí đầu ra là vị trí của ký tự JS cuối cùng trong chuỗi.


### 3. Cắt chuỗi (Cut String)
a) Cắt từ vị trí thứ 4 đến vị trí thứ 6

	console.log(myString.slice(4,6));

b) Cắt từ vị trí thứ 4 trở về sau

	console.log(myString.slice(4));

c) Cắt từ đầu đến cuối

	console.log(myString.slice(0));

d) Cắt ngược từ trái sang phải

	console.log(myString.slice(-3, -1));


### 4. Ghi đè (Replace)

a) Nếu có nhiều ký tự JS trong chuỗi thì nó sẽ thay thế cho ký tự JS đầu tiên

	console.log(myString.replace("JS", "Javascript"));

b) Thay đổi tất cả ký tự JS trong chuỗi

	console.log(myString.replace(/JS/g, "Javascript"));

### 5. Biến chuỗi thành chữ in (Convert to uppercase)
	console.log(myString.toUpperCase());


### 6. Biến chuỗi thành chữ thường (Convert to lowercase)
	console.log(myString.toLowerCase());


### 7. Xử lý khoảng trắng đầu và cuối chuỗi (Trim)
	console.log(myString.trim());

### 8. Cắt 1 chuỗi thành 1 Array
b) Cắt chuỗi thành 1 Array chứa từng chữ
	
	var languages = 'Javascript, PHP, Ruby';  // Cần 1 điểm chung là dấu phẩy và dấu cách
	console.log(languages.split(', ')); // Cắt từng chữ


b) Cắt chuỗi thành 1 Array chứa từng ký tự của Javascript

	var languages1 = 'Javascript';
	console.log(languages1.split(''));


### 9. Lấy 1 ký tự bởi 1 vị trí cho trước
### Cách 1:
 
	const myString2 = "Son Dang";
	console.log(myString2.charAt(2));

Trong trường hợp truyền vào 1 index không tồn tại thì cho ra chuỗi rỗng

### Cách 2:

	console.log(myString2[1]);

Trong trường hợp truyền vào 1 index không tồn tại thì cho ra undefinded

---

## Bài 28: Kiểu số
### 1. Cách khai báo

Cách thông thường khi ta khai báo một số. Ví dụ là: 1000000 (một triệu)

	var million = 1000000;
	
Cũng là khai báo số 1000000 nhưng có cách viết khác. Bạn có thể thêm chữ e vào sau số 1 và chỉ định số số không phía sau chữ e như sau:

	var million = 1e6; // tương tự: 1000000
	var billion = 2e9; // tương tự: 2000000000 (hai tỉ)

### 2. Đối tượng Number

Phương thức        	| Vai trò          	|
--------------------|------------------	|
Number.isFinite()	|Xác định xem giá trị đã cho có phải là số hữu hạn hay không. Trả về boolean
Number.isInteger()	|Xác định xem giá trị đã cho có phải là số nguyên hay không. Trả về boolean
Number.parseFloat()	|Chuyển đổi chuỗi đã cho thành một số dấu phẩy động
Number.parseInt()	|Chuyển đổi chuỗi đã cho thành một số nguyên
Number.prototype.toFixed()	|Chuyển đổi và trả về chuỗi đại diện cho số đã cho, có số chữ số chính xác sau dấu thập phân
Number.prototype.toString()|	Chuyển đổi và trả về số đã cho dưới dạng chuỗi

### 3. Ví dụ
	
	Number.isFinite(2 / 0); // false
	Number.isFinite(20 / 5); // true
	Number.isFinite(0 / 0); // false
	
	Number.isInteger(999999999); // true
	Number.isInteger(0.2);       // false
	Number.isInteger(Math.PI);   // false
	
	Number.parseFloat('10') // 10
	Number.parseFloat('10.00') // 10
	Number.parseFloat('238,21') // 238
	Number.parseFloat('237.22') // 237.22
	Number.parseFloat('34 56 78') // 34
	Number.parseFloat(' 37 ') // 37
	Number.parseFloat('18 is my age') // 18
	
	Number.parseInt('10') // 10
	Number.parseInt('10.00') // 10
	Number.parseInt('238,21') // 238
	Number.parseInt('237.22') // 237
	Number.parseInt('34 56 78') // 34
	Number.parseInt(' 37 ') // 37
	Number.parseInt('18 is my age') // 18
	
	var numberObject = 1234.56789;
	
	numberObject.toFixed(); // '1235'
	numberObject.toFixed(1); // '1234.6'
	numberObject.toFixed(6); // '1234.567890'
	
	(11).toString();    // '11'
	(18).toString();     // '18'
	(17.3).toString();   // '17.3'
	
	
---
## Bài 29: Số và làm việc với số
### 1. Cách tạo giá trị Number
### Cách 1:
 
	var age = 18;
	var PI = 3.14;

### Cách 2: 

	var otherNumber = new Number(9);

### 2. Kiểm tra có phải là Number hay không

	var result = 20/'ABC';
	console.log(result); // cho ra kết quả là 1 số không hợp lệ
	console.log(isNaN(result)); // Check kết quả là NaN

### 3. Làm việc với Number

a) Chuyển Number sang String (To String)

	console.log(age.toString());

b) Làm tròn số thập phân (To fixed)

	console.log(typeof PI.toFixed());
	
- Khi dùng to fixed thì giá trị được chuyển thành String
- Với giá trị <0.5 thì làm tròn dưới,  >=0.5 thì làm tròn trên
- Rút gọn bao nhiêu số thập phân thì thêm vào trong PI.toFixed(2), ở đây là làm tròn 2 số thập phân
	
---
## Bài 30: Mảng
### 1. Cách tạo mảng
### Cách 1:

	var languages = [
	    'Javascript',
	    'PHP',
	    'Rubby',
	    'Dart',
	    null,
	    undefined,
	    function() {}, // function
	    {} // object trống
	];

### Cách 2: (tham khảo chứ không dùng cách này)

	var languages1 = new Array(
	    'Javascript',
	    'PHP',
	    'Rubby',
	    'Dart',
	    null,
	    undefined,
	    function() {
	    }, // function
	    {} // object trống
	    123
	);
	
--

	console.log(typeof languages);
	
Kiểm tra xem có phải là Array hay không?

Kiểm tra để biết từng trường hợp có nên sử dụng kiểu dữ liệu này hay không?

### Chú ý:
Khi chúng ta sử dụng typeof thì cả {} và Array đều trả về kiểu dữ liệu là Object.

a) Kiểm tra xem có phải là Array hay không? (boolean)
	
	console.log(Array.isArray(languages)); // là Array
	console.log(Array.isArray({})); // không là Array

b) Kiểm tra độ dài của mảng:

	console.log(languages.length); // kiểm tra độ dài của mảng

c) Lấy phần tử theo Index:

	console.log(languages[2]);

---

## Bài 31: Làm việc với mảng

	var languages = [
	     'Javascript',
	     'PHP',
	     'Ruby'
	 ];

### 1. Chuyển sang dạng String (To String)

	console.log(languages.toString());

### 2. Chuyển sang dạng String và có dấu ngăn cách (Join)
	
	console.log(languages.join('-'));

### 3. Xóa element cuối mảng, return element đã xóa đó (Pop)
	
	console.log(languages.pop());
	console.log(languages); // Mảng còn lại

### 4. Thêm 1 hoặc nhiều element vào cuối mảng (Push)
	
	console.log(languages.push('Dart','Java'));
	console.log(languages);
  
### 5. Xóa element đầu mảng, return element đã xóa đó (Shift)
	
	console.log(languages.shift());
	console.log(languages);

### 6. Thêm 1 hoặc nhiều element vào đầu mảng (Unshift)

	console.log(languages.unshift('Dart','Java'));
	console.log(languages);

### 7. Xóa, cắt, chèn 1 phần tử mới vào mảng (Splicing)

	languages.splice(1,1);
splice(vị trí đặt con trỏ, số phần tử muốn xóa kể từ vị trí đặt con trỏ)

Vị trí đặt con trỏ có thể là 0, 1, 2, 3



### Xóa phần tử cuối cùng của mảng

	languages.splice(-2);

splice(vị trí đặt con trỏ, vị  trí con trỏ của phần tử thứ 2 đếm từ cuối mảng lên dùng số âm)

Vị trí đặt con trỏ cuối có thể là -1, -2, -3


--

	languages.splice(1, 0, 'Dart');
	
splice(vị trí đặt con trỏ, số phần tử muốn xóa kể từ vị trí đặt con trỏ, phần tử muốn chèn vào vị trí vừa xóa)


### 8. Nối 2 mảng với nhau (Concat)

	var languages2 = [
	    'Dart',
	    'Java'
	]
	console.log(languages.concat(languages2)); // Nối theo thứ tự

### 9. Copy 1 element của mảng (Slicing)

	console.log(languages.slice(1,2));
	slice (vị trí đặt con trỏ điểm đầu, vị trí đặt con trỏ điểm cuối)

### Copy cả mảng

	console.log(languages.slice(0));

---
## Bài 32: Hàm (Function)

### 1. Hàm?
- 1 khối mã
- Làm 1 việc cụ thể

### 2. Các loại hàm
- Built-in
- Tự định nghĩa

### 3. Tính chất
- Không thực thi khi định nghĩa
- Sẽ thực thi khi được gọi
- Có thể nhận tham số
- Có thể trả về 1 giá trị 

### 4. Đặt tên hàm
- Tên hàm có thể chứa chữ cái từ a-z, A-Z, 0-9, _, $
- Tên hàm không được đặt số ở đầu tiên

### Ví dụ:

	function showDialog() {
	    alert('Hi xin chào các bạn!');
	}

Gọi hàm

	showDialog();

---

## Bài 33: Tham số trong Function

- Khi chúng ta định nghĩa function, giá trị nằm trong function gọi là tham số.
- Khi chúng ta gọi đến function và truyền giá trị vào, giá trị đó gọi là đối số.
- Giá trị mà chúng ta truyền vào đó không giới hạn kiểu dữ liệu
- Tham số được sử dụng trong function, khi đưa ra ngoài sẽ không sử dụng được nữa

### Ví dụ:

    function writeLog(message) {
        console.log(message)
    }
    writeLog('Test Message');

### a) Truyền 2 tham số

    function writeLog(message, message2) {
        console.log(message)
        console.log(message2)
    }
    writeLog('Test Message', 'Test_2');

### b) Sử dụng If

    function writeLog(message, message2) {
        if (message) {
            console.log(message)
        }
        if (message2) {
            console.log(message2)
        }
    }
    writeLog('Test Message', 'Test_2');

### c) Đối tượng Arguments (Array)

	   function writeLog(){
	        console.log(arguments)
	    }
	    writeLog('Log 1', 'Log 2', 'Log 3');

Không cần phải truyền tham số vào function mà chỉ cần sử dụng arguments. Ở ngoài function, chúng ta gọi lại function và truyền bao nhiêu đối số cũng được.

### d) Vòng For of

    function writeLog() {
        for (var param of arguments) {
            console.log(param)
        }
    }
    writeLog('Log 1', 'Log 2', 'Log 3');

Chạy vòng for và lấy element đầu tiên của Arguments dưới hàm writeLog sau đó truyền vào param. Sau đó chạy vào đoạn code console.log(param) nằm trong function. Có bao nhiêu element trong argument thì chạy bấy nhiêu lần vòng for.

### e) Cho 1 chuỗi myString rỗng. Cứ mỗi lần chạy vòng for thì sẽ cộng thêm 1 param vào myString.

	function writeLog() {
	  myString = "";
	  for (var param of arguments) {
	    myString += `${param} - `;
	  }
	  console.log(myString);
	}
	writeLog("Log 1", "Log 2", "Log 3", "Log 4");
	
---

## Bài 34: Tham số trong Function

### Lấy kết quả của người dùng nhấn vào OK hay Cancel

	var isConfirm = confirm('Message?');
	console.log(isConfirm);

### Ví dụ:

	function cong(a, b) {
	    return a + b;
	}
	var result = cong(2, 8);
	console.log(result);

Khi chúng ta không dùng return thì sẽ trả về undefinded.

Return là hành động cuối cùng của function, những hành động sau return đều bị disable.

Có thể trả về bất kỳ dữ liệu gì, có thể là mảng `[a, b]` hoặc `return a.toString() + b.toString()`
 
 ---
 
## Bài 35: Hiểu hơn về Function

### 1. Khi function đặt trùng tên

	function showMessage() {
	  console.log("Message 1");
	}
	function showMessage() {
	  console.log("Message 2");
	}
	function showMessage() {
	  console.log("Message 3");
	}
	showMessage();

Chương trình sẽ chạy function cuối cùng.

### 2. Khai báo biến trong hàm

	function showMessage() {
	    var fullName = 'Son Dang';
	    console.log(fullName);
	}
	showMessage();

Khi định nghĩa 1 biến trong hàm thì phạm vi sử dụng của biến đó cũng chỉ trong hàm.

### 3. Định nghĩa hàm trong hàm

	function showMessage() {
	  function showMessage2() {
	    console.log("Message 2");
	  }
	  showMessage2();
	}
	showMessage();


## Bài 37: Các loại Function

### 1. Declaration Function

	function showMessage(){
	}
	
- Định nghĩa 1 function
- Bắt buộc đặt tên

### Có thể gọi trước khi đến định nghĩa function

	showMessage()
	function showMessage(){
	}

### 2. Expression function

	var showMessage2 = function() {
	}

- Được gán cho 1 biến
- Có thể đặt tên hoặc không 

### Ví dụ:

	setTimeout(function() {
	});
	
	var myObject = {
	    myFunction: function() {}
	}

---

## Bài 38: Object

Lữu trữ thông tin của 1 đối tượng cụ thể

	emailKey = 'email';
	
emailKey là Key
‘email’ là value

	var myInfo = {
	  name: 'Son Dang',
	  age: 18,
	  address: 'Ha Noi, VN',
	}

Cách đặt tên key cũng giống như đặt tên biến, nếu muốn đặt full-name thay vì name thì để ‘full-name’, vẫn hoạt động bình thường.

### Thêm 1 key & value vào object

	myInfo.email = 'sondn@fullstack.edu.vn';

### Thêm 1 key & value nhưng key sai quy tắc đặt tên

	myInfo.['my-email'] = 'sondn@fullstack.edu.vn'

### Lấy value ra ngoài
### Cách 1: (bình thường dùng cách này)

	console.log(myInfo.name); 
	
### Cách 2:

	console.log(myInfo['name']);

Key không tồn tại thì trả về undefinded


	var myInfo = {
	  name: 'Son Dang',
	  age: 18,
	  address: 'Ha Noi, VN',
	}
	var myKey = "address";
	
### Để lấy address trong object myInfo thông qua biến myKey nằm bên ngoài object.

	console.log(myInfo[myKey]);

Không dùng `console.log(myInfo['myKey']);` vì nó sẽ tìm myKey trong object myInfo

### Xóa age trong object myInfo

	delete myInfo.age;

### Function nằm trong object

	var myInfo = {
	  name: "Son Dang",
	  age: 18,
	  address: "Ha Noi, VN",
	  getName: function () {
	    return this.name; // tương đương với myInfo.name
	    // khi đổi tên myInfo thì phải đổi hết tất cả, nếu dùng this thì không phải thay đổi nhiều
	  },
	};
	console.log(myInfo.getName());

### Chú ý:

- Function nằm trong object gọi là phương thức (method)

- Những trường hợp còn lại gọi là thuộc tính (property)

---

## Bài 39: Object Constructor

**Object Constructor** hay bản thiết kế, cấu trúc ban đầu của object

	function User(firstName, lastName, avatar) {
	  this.firstName = firstName;
	  this.lastName = lastName;
	  this.avatar = avatar;
	  }
	}

	var author = new User('Son', 'Dang', 'Avatar'); 
	var user = new User('Vu', 'Nguyen', 'Avatar'); 
ở đây, author hay user là object, còn User là object constructor.

### Thêm thuộc tính vào đối tượng

	author.title = 'Chia sẻ tại F8';
	user.comment = 'Liệu có khoá'


### Phương thức trong object

	function User(firstName, lastName, avatar) {
	  this.firstName = firstName; 
	  this.lastName = lastName;
	  this.avatar = avatar;
	
	  this.getName = function() {
	    return `${this.firstName} ${this.lastName}`; 
	  }
	}

this trong phương thức là this của getName

### Gọi phương thức ra như bình thường

	console.log(author.getName());
	console.log(user.getName());
	
---

## Bài 40: Object Prototype

**Object prototype** là thuộc tính cấu thành Object Constructor

	function User(firstName, lastName, avatar) {
	  this.firstName = firstName; 
	  this.lastName = lastName;
	  this.avatar = avatar;
	  this.getName = function() {
	    return `${this.firstName} ${this.lastName}`;
	  }
	}

ở đây `this.firstName = firstName` là 1 object prototype

### Thêm 1 prototype vào Object constructor

	User.prototype.className = 'F8';
	User.prototype.getclassName = function() {
	  return this.className;
	};

ở đây chúng ta đang thêm className và getclassName vào object constructor

---

## Bài 41: Đối tượng Date

	var date = new Date();
	var month = date.getMonth();
	var year = date.getFullYear(); 
	var day = date.getDate();
	var hour = date.getHours();
	var minutes = date.getMinutes();
	
	console.log(date); //in ra thời gian hiện tại
	console.log(month) + 1; // in ra tháng nhưng phải +1 vì tháng này nó đếm từ 0
	console.log(year); // in ra năm hiện tại
	console.log(hour); // in ra giờ hiện tại, ví dụ 9h30 thì là 9h
	console.log(minutes); // in ra phút hiện tại

	console.log(`${day}/${month}/${year}`); // in ra full
	ngày/tháng/năm

### Documentation:
[https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Date 
]()

---

## Bài 42: Câu lệnh rẽ nhánh If - Else

	var date = 4; // giá trị giao động từ 2-8
	if (date === 2){
	    console.log('Hôm nay là thứ 2');
	} else if (date === 3){
	    console.log('Hôm nay là thứ 3');
	} else if (date === 4){
	    console.log('Hôm nay là thứ 4');
	} else {
	    console.log('Không biết'); // else cuối cùng nếu các dòng kia không thỏa mãn giá trị đã cho ban đầu
	}

---

## Bài 43: Câu lệnh rẽ nhánh Switch – Case

	var date = 10;
	
	switch(date)  {
	    case 2: 
	        console.log('Hôm nay là thứ 2');
	        break;
	    case 3: 
	        console.log('Hôm nay là thứ 3');
	        break;
	    case 4: 
	        console.log('Hôm nay là thứ 4');
	        break;
	    case 5: 
	        console.log('Hôm nay là thứ 5');
	        break;
	    default: 
	        console.log('Không biết');
	}

### Các trường hợp nào thì sử dụng If-Else/Switch-Case
- Sử dụng If – Else khi bài toán yêu cầu so sánh tính đúng sai, xuất hiện toán tử <> !== 
- Sử dụng Switch – Case khi được cho các giá trị
- Sử dụng Switch – Case khi ít hơn 3 case

---

## Bài 44: Toán tử 3 ngôi

	var course = {
	    name: 'Javascript',
	    coin: 0
	}
	var result = course.coin > 0 ? `${course.coin} Coins` : 'Miễn phí';
	console.log(result);

**Cấu trúc: điều kiện ? case 1 : case 2**
### Chú ý:
Sử dụng toán tử 3 ngôi trong những trường hợp đơn giản

---

## Bài 46, 47, 48: Vòng lặp For

### Lặp với điều kiện đúng
Ví dụ 1:

	for (var i = 1; i <= 1000; i++) {
	    console.log(i);
	}

Ví dụ 2:

	var myArray = [
	    'Javascript',
	    'PHP',
	    'Java',
	    'Dart',
	    'Rubby'
	];
	var arrayLength = myArray.length;
	for (var i = 0; i < arrayLength; i++) {
	    console.log(myArray[i]);
	}

---

## Bài 49: Vòng lặp For/in

Lặp qua từng key của đối tượng

### Với Object

	var myInfo = {
	    name: 'Son Dang',
	    age: 18,
	    address: 'Ha Noi, VN'
	};
	for (var key in myInfo) {
	    console.log(myInfo[key]);
	}

### Với Array

	var languages = [
	    'Javascript',
	    'PHP',
	    'Ruby'
	];
	for (var key in languages) {
	    console.log(languages[key]);
	}

### Với String

	var languages = 'Javascript';
	for (var key in languages) {
	    console.log(languages[key]);
	}
	
In ra từng ký tự của chuỗi

---

## Bài 50: Vòng lặp For/of

Lặp qua từng value của đối tượng

### Với Array

	var languages = [
	    'Javascript',
	    'PHP',
	    'Java'
	];
	for (var value of languages) {
	    console.log(value); // Lấy từng phần tử của 1 mang
	}

### Với String

	var languages = 'Javascript';
	for (var value of languages) {
	    console.log(value); // Lấy từng phần tử của 1 chuoi
	}
	
In ra từng ký tự của chuỗi

### Với Object

	var myInfo = {
	        name: 'Son Dang',
	        age: 18
	};
	for (var value of Object.values(myInfo)) {
	    console.log(value); // Lấy từng phần tử của 1 Object
	}

----

## Bài 51: Vòng lặp While
Ví dụ 1:

	var i = 0;
	while (i<1000) {
	    i++;
	    console.log(i);
	}

Ví dụ 2:

	var myArray = [
	    'Javascript',
	    'PHP',
	    'Rubby'
	];
	var i = 0;
	while (i<myArray.length) {
	    console.log(myArray[i]);
	    i++;
	}
	
--- 

## Bài 52: Vòng lặp Do/While

	var i = 0;
	do {
	    i++;
	    console.log(i);
	} while (i <10);

Vòng lặp Do/While sẽ kiểm tra điều kiện vào lần thứ 2, lần đầu tiên chạy vào do{} nên không kiểm tra điều kiện.
 


### Bài toán:
Chức năng nạp thẻ cào, đôi khi mạng sẽ yếu sẽ không nạp thẻ thành công. Trong thực tế chúng ta sẽ có 3 lần nạp, sau 3 lần mới khóa.

	var i = 0;
	var isSuccess = false; 
	do {
	    i++;
	    console.log('Nạp thẻ lần ' +i);
	    // Thành công
	    if (true) {
	        isSuccess = true;
	    }
	} while (!isSuccess && i < 3)

---

## Bài 53: Break và Continue trong vòng lặp

### In từ 0 đến 5

	for (var i = 0; i < 10; i++) {
	    console.log(i);
	    if (i >= 5) {
	        break;
	    }
	}

### In số chẵn

	for (var i = 0; i < 10; i++) {
	  if (i % 2 !== 0) {
	    continue;
	  }
	  console.log(i);
	}
	
- Khi i = 0, i chia cho 2 dư 0, sai với điều kiện của If() nên chạy xuống in console.log(i) in ra 0.
- Khi I = 1, I chia cho 2 với số dư khác 0, đúng với điều kiện của If(), chạy xuống continue rồi quay lại lại chạy tiếp vòng lặp for.

---

## Bài 54: Vòng lặp lòng nhau (Nested loop)

	var myArray = [
	    [1, 2], 
	    [3, 4],
	    [5, 6]
	];
	for (var i = 0; i < myArray.length; i++) {
	    for (var j = 0; j < myArray[i].length; j++) {
	        console.log(myArray[i][j]);
	    }
	}

---

## Bài 55: Thêm ví dụ về vòng lặp
### In từ 100 về 1

	for (var i = 100; i > 0; i--) {
	    console.log(i);
	}

### In ra các giá trị 0, 5, 10, 15

	for (var i = 0; i <= 100; i += 5) {
	  console.log(i);
	}

---

### Bài 56: Làm việc với mảng (phần 2)

	var courses = [
	  {
	    id: 1,
	    name: "Javascript",
	    coin: 250,
	  },
	  {
	    id: 2,
	    name: "HTML, CSS",
	    coin: 0,
	  },
	  {
	    id: 3,
	    name: "Rubby",
	    coin: 0,
	  },
	  {
	    id: 4,
	    name: "PHP",
	    coin: 400,
	  },
	  {
	    id: 5,
	    name: "ReactJS",
	    coin: 500,
	  },
	  {
	    id: 6,
	    name: "Rubby",
	    coin: 0,
	  },
	];

### 1. forEach()
	
	courses.forEach(function(course, index) {
	    console.log(index, course);
	});

**Chức năng: duyệt  từng phần tử của mảng**

- Phương thức thì dùng dấu chấm
- Hàm được truyền dưới dạng tham số được gọi là callback

### 2. Every()
**Chức năng: Kiểm tra tất cả phần tử của 1 mảng thỏa mãn 1 điều kiện gì đó**

- every() trả về giá trị là boolean
- Duyệt phần tử đầu tiên, nếu phần tử đầu tiên sai với điều kiện thì dừng và in ra False ngay lập tức
- Nếu không thì vẫn cứ duyệt như thường đến khi nào tìm được False, không tìm ra ra False thì in True

### Bài toán:
Bài toán đặt ra là kiểm tra xem toàn bộ khóa học này có phải là miễn phí hay không?
Nếu có thì trả về True, không thì trả về False.

	var isFree = courses.every(function(course, index) {
	    return course.coin === 0;
	}); // Check hết vòng trên, ra kết quả thì in dòng dưới này
	console.log(isFree);

### 3. Some()
**Nếu 1 phần tử trong mảng thỏa mãn điều kiện thì in ra ngay là đúng mà không cần quan tâm đến những phần tử còn lại.**

- some() trả về giá trị là boolean
-  Duyệt phần tử đầu tiên, nếu phần tử đầu tiên sai với điều kiện thì tiếp tục duyệt đến các phần tử tiếp theo
-  some() sẽ duyệt đến khi nào gặp phần tử thỏa mãn điều kiện sẽ in ra là True ngay lập tức mà không cần quan tâm đến các phần tử tiếp theo đúng hay sai. Trường hợp không tìm ra phần tử thỏa mãn điều kiện thì báo False cả hàm.

### Ví dụ: 

	var isFree = courses.some(function(course, index) {
	    return course.coin === 0;
	}); // Check hết vòng trên, ra kết quả thì in dòng dưới này
	
	console.log(isFree);

### 4. Find()
**Chức năng:
- Tìm 1 phần tử thỏa mãn điều kiện trong mảng
- Trả về duy nhất 1 phần tử, nếu có 1 phần tử khác đã trùng thì cũng chỉ trả về phần tử đầu tiên**

### Ví dụ:

	var course = courses.find(function(course, index) {
	    return course.name === 'Rubby';
	}); // Check hết vòng trên, ra kết quả thì in dòng dưới này
	console.log(course);

### 5. Filter()
**Chức năng: Tìm tất cả các phần tử thỏa mãn 1 điều kiện trong mảng**
	
	var listCourse = courses.filter(function (course, index) {
	  return course.coin === 0;
	}); // Check hết vòng trên, ra kết quả thì in dòng dưới này
	console.log(listCourse);

---

## Bài 57: Array map() method
**Chức năng: chỉnh sửa element của 1 Array**

	var courses = [
	    {
	        id: 1,
	        name: 'Javascript',
	        coin: 250
	    }, 
	    {
	        id: 2,
	        name: 'HTML, CSS',
	        coin: 0
	    },
	    {
	        id: 3,
	        name: 'Rubby',
	        coin: 0
	    },
	    {
	        id: 4,
	        name: 'PHP',
	        coin: 400
	    },
	    {
	        id: 5,
	        name: 'ReactJS',
	        coin: 500
	    },
	    {
	        id: 6,
	        name: 'Rubby',
	        coin: 0
	    },
	];

### Bài toán: 
Thêm trước name cụm từ khóa học, ví dụ ‘Rubby’ thành ‘Khóa học Rubby’.

Trên từng element, thêm 1 key là coinText: “Giá: 0”

	var newCourses = courses.map(courseHandler); 
	console.log(newCourses);
	
\- Đối số nằm trong map() phải là 1 function (phương thức), nếu để trống thì kết quả trả về cho newCourses là undefinded

\- Phương thức map sẽ return về cho biến newCourses 1 mảng có số lượng phần tử bằng đúng với số lượng phần tử của mảng cũ (courses)

\- map() sẽ duyệt qua từng phần tử của mảng cũ, mỗi khi duyệt đến phần tử nào, map() sẽ gọi đến function courseHandler

	function courseHandler(course, index) {
	   return {
	       id: course.id,
	       name: `Khóa học: ${course.name}`,
	       coin: course.coin,
	       coinText:  `Giá: ${course.coin}`,
	       index: index, // có thể truyền thêm 1 tham số index
	       originArray: course
	
	   };
	};

Chúng ta return cái gì ở function courseHandler thì biến newCourses sẽ nhận được lại y chang như vậy theo từng vị trí của các phần tử trong mảng. Ví dụ, chúng ta không return gì thì newCourses nhận được undefinded, chúng ta return về courses thì newCourses nhận được mảng cũ. 

\- Tham số ở trong courseHandler được ngầm hiểu là từng phần tử của mảng courses, vì vậy chúng ta đặt tên gì cũng được, ở đây chúng ta đặt tên là course.

\-Tham số index có hay không cũng được.

### Bài toán: 
Chỉ trả về tên khóa học, biến array thành string

	function F8Handler(course, index){
	    return  `<h2>${course.name}</h2>`;
	    // Nhận 1 mảng toàn thẻ h2
	};
	
	var newF8 = courses.map(F8Handler);
	console.log(newF8.join('')); // nối Array với 1 chuỗi rỗng thì sẽ tạo ra 1 string

---

## Bài 58, 59: Array reduce() method
Khi muốn nhận về 1 giá trị duy nhất sau khi tính toán, xử lý trên 1 phần tử của Array.

	var courses = [
	    {
	        id: 1,
	        name: 'Javascript',
	        coin: 100
	    }, 
	    {
	        id: 2,
	        name: 'HTML, CSS',
	        coin: 200
	    },
	    {
	        id: 3,
	        name: 'Rubby',
	        coin: 220
	    },
	    {
	        id: 4,
	        name: 'PHP',
	        coin: 200
	    },
	    {
	        id: 5,
	        name: 'ReactJS',
	        coin: 480
	    }
	];

### Bài toán: Tính tổng số coin của khóa học
### Sử dụng vòng lặp For/of

	var totalCoin = 0; // biến lưu trữ
	for (var course of courses) { // lặp qua các phần tử
	    totalCoin += course.coin; // thực hiện lưu trữ
	} 
	console.log(totalCoin);

### Sử dụng phương thức reduce()

	var totalCoin = courses.reduce(coinHandler, 0);
	console.log(totalCoin);
	 
	function coinHandler(accumulator, currentValue, currentIndex, originArray){
	    var total = accumulator + currentValue.coin;
	    return total;
	}
Trong phương thức reduce có 2 đối số đó là 1 function (phương thức) và 1 initialValue (giá trị khởi tạo)

Cấu trúc: `coinHandler (biến lưu trữ, giá trị hiện tại, chỉ mục, array)`

`accumulator`: giá trị khởi tạo ban đầu bằng 0, được định nghĩa bởi đối số trong hàm reduce()

`currentValue`: gía trị của từng phần tử của mảng

`currentIndex`: chỉ mục

`originArray`: mảng gốc

`reduce()` là phương thức

Phương thức nằm trong `reduce` gọi là `callback`

### Có thể viết lại như này:
	
	var totalCoin = courses.reduce(function(total, course) {
	    console.log(i, total, course);
	    return total + course.coin;
	}); 
### Lưu ý
- Initial Value là giá trị không bắt buộc
- Khi có giá trị khởi tạo, nó sẽ lấy giá trị khởi tạo đó cho lần chạy đầu tiên. Ví dụ, initial value là 0 thì lần chạy đầu tiên nó lấy giá trị khởi tạo bằng 0.
- Khi không có giá trị khởi tạo, nó sẽ lấy phần tử đầu tiên của mảng làm giá trị khởi tạo. Lúc này currentValue là phần tử thứ 2. Vì vậy, ngay từ lần chạy đầu tiên nó đã lấy element1 làm giá trị khởi tạo và element2 làm current value. Thành ra chúng ta mất đi 1 lần chạy, cũng không ảnh hưởng đến kết quả. Hơn nữa kết quả chúng ta muốn nhận được là tổng số coin, nếu không đặt initial value thì kết quả chúng ta nhận được là object, sai với mong muốn.
- Không phải bài toán nào chúng ta cũng bỏ innitial value đi được
- Muốn nhận dữ liệu kiểu gì thì đặt innitial value là kiểu dữ liệu đó.



### So sánh giữa vòng lặp bình thường và vòng lặp nâng cao
1. Dễ hiểu: vòng lặp bình thường
2. Ngắn gọn: vòng lặp nâng cao
3. Hiệu năng: vòng lặp bình thường nhưng không đáng kể


### Ví dụ 1: Tính tổng các số trong mảng

	var numbers = [100, 200, 220, 200, 480];
	var totalCoin = numbers.reduce(function (total, number) {
	    return total + number;
	});
	console.log(totalCoin);

### Ví dụ 2: Flat - "Làm phẳng" mảng từ Depth array - "Mảng sâu"

	var depthArray = [1, 2, [3, 4], 5, 6, [7, 8, 9]];
	
	var flatArray = depthArray.reduce(function(flatOutput, depthItem){
	    // flatOutput
	    // depthItem: currenValue
	    return flatOutput.concat(depthItem); // nối mảng
	}, []);

### Ví dụ 3: Lấy ra những khóa học và đưa vào 1 mảng mới

	var topics = [
	    {
	        topic: "Front-end",
	        courses: [
	            {
	                id: 1,
	                title: "HTML, CSS"
	            },
	            {
	                id: 1,
	                title: "Javascript"
	            }
	        ]
	    },
	    {
	        topic: "Back-end",
	        courses: [
	            {
	                id: 1,
	                title: "PHP"
	            },
	            {
	                id: 1,
	                title: "NodeJS"
	            }
	        ]
	    },
	];
	
	var newCourse = topics.reduce(function(courses, topic){
	    return courses.concat(topic.courses);
	}, []);
	    console.log(newCourse);
	
	    var htmls = newCourse.map(function(course){
	        return `
	        <div>
	            <h2>${course.title}</h2>
	            <p>${course.id}</p>
	        </div>
	        `;
	    });
	    console.log(htmls.join(''));
	    
---

## Bài 61: String/Array includes() method
Include là hàm, phương thức của String/Array
 
### Với String
Trả về true hoặc false

	var title = 'Responsive web design';
	console.log(title.includes('web'));


### Tìm kiếm từ vị trí nào
Đối số thứ 2 là vị trí bắt đầu tìm kiếm, mặc định bằng 0

	console.log(title.includes('Responsive', 1));

### Với Array
Trả về true hoặc false

	var courses = [‘Javascript’, ‘PHP’, ‘Dart’];
	console.log(courses.includes(‘Rubby’));



### Tìm kiếm từ vị trí nào
Đối số thứ 2 là vị trí bắt đầu tìm kiếm, mặc định bằng 0

	console.log(courses.includes("Javascript", 0));

---
 
## Bài 62: Math Object

	- Math.PI
	- Math.round()
	- Math.abs()
	- Math.ceil()
	- Math.floor()
	- Math.random()
	- Math.min()
	- Math.max()

### Ví dụ:
	console.log(Math.PI); // Đưa ra giá trị của số PI
	console.log(Math.round(1.3)); // Làm tròn số thập phân
	console.log(Math.abs(-2)); // Giá trị tuyệt đối
	console.log(Math.ceil(5.1)); // Làm tròn trên, phải lớn hơn 0
	console.log(Math.floor(4.999999999)); // làm tròn dưới
	console.log(Math.random()); // Trả về 1 số thập phân ngẫu nhiên nhỏ hơn 1
	console.log(Math.floor(Math.random()*100)); // Tạo ra số ngẫu nhiên

### Bài toán 1:
Tạo ra số từ 1 đến 5  (đã được làm tròn), ứng với index của các phần tử trong mảng sẽ cho ra số coin ngẫu nhiên

	var random = Math.floor(Math.random() * 5);
	var bonus = [
	    '10 coin',
	    '20 coin',
	    '30 coin',
	    '40 coin',
	    '50 coin'
	];
	console.log(bonus[random]);

**Giải thích quá trình**

	var temp = Math.random(); // Tạo ra 1 số thập phân nhỏ hơn 1
	console.log(temp);
	console.log(temp * 6); // Trường hợp số ngẫu nhiên ra 0.9999 mà nhân với 6 thì cũng chỉ bằng 5.9999, mà 5.9999 làm tròn dưới là 5. Vậy nên nhân với 6 rồi làm tròn, ngẫu nhiên sẽ ra được từ 1 đến 5.

### Bài toán 2:
Quay ra tỉ lệ thấp

	var random = Math.floor(Math.random() * 100); // Tạo ra random nhỏ hơn 1, cao nhất là 0.99, sau khi nhân với 100 thì cao nhất là 99, chúng ta sẽ có 99 trường hợp từ 0 - 99
	if (random < 5) {
	    console.log('Cường hóa thành công!'); // Nếu random nhỏ hơn thì mới hiện thông báo này, tỉ lệ rất thấp để hiện thông báo
	}

### Math.min()
	console.log(Math.min(-100, 1, 90, 50, 40));

### Math.max()
	console.log(Math.max(-100, 1, 90, 50, 40));

---


## Bài 63, 64: Callback
**Callback** là hàm và được truyền qua đối số, được gọi lại trong hàm nhận đối số.

	function myCallback(value) {
	    console.log('Value:', value)
	}
	myCallback(123);

Thông thường chúng ta sẽ gọi lại function `myCallback` bằng cách ngoài function `myCallback` chúng ta gọi lại `myCallback` và truyền giá trị vào bên trong, chúng ta có:

	myCallback(123);
	
Khi chúng ta cho giá trị là `123` thì ở `console.log('Value:', value)` sẽ in ra dòng `Value: 123`

Thay vì chúng ta gọi ở bên ngoài function `myCallback`, chúng ta gọi từ 1 function khác.

	function myFunction(param) {
	}
	function myCallback(value) {
	    console.log('Value:', value)
	}
	myFunction(myCallback);

Ta viết thêm 1 function là `myFunction`, ta truyền tham số là `param`, ta chạy function `myFunction` bằng cách gọi `myFunction()` bên ngoài với giá trị truyền vào là `myCallback`. Khi đó `myCallback` là `param` và ta muốn chạy `myCallback()` bên trong function `myFunction` thì ta viết `param()`, nó cũng giống như là `myCallback()`. Sau đó chúng ta truyền giá trị vào `param` thành `param('Học lập trình')`.
Ta được:

	function myFunction(param) {
	    param('Học lập trình');
	}
	function myCallback(value) {
	    console.log('Value:', value)
	}
	myFunction(myCallback);

Và in ra kết quả là `Value: Học lập trình.`

**Tóm lại:**
Ta gọi 1 Function, rồi ta truyền nó qua đối số của 1 function khác thì chúng ta có thể gọi nó là `callback`, ở đây myCallback được truyền qua đối số của `myFunction` rồi chạy trong `myFunction`.

![](https://i.ibb.co/YLCZ8b4/Screen-Shot-2021-07-01-at-21-14-29.jpg)

---
## Bài 65: Empty elements of array
	
	var courses = ["Javascript", "PHP"];
	courses.length = 10;
	console.log(courses);

Không phải lúc nào thuộc tính length cũng quyết định độ dài của mảng đó.

![](https://i.ibb.co/p1QBMPx/Picture1.jpg)

---
## Bài 66: My forEach() method
### Ví dụ:
	var courses = ["Javascript", "PHP", "Rubby"];
	var output = courses.forEach2(function (course, index, array) {
	  console.log(course, index, array);
	});

Khi chúng ta khởi tạo 1 phương thức cho `Array Constructor`, khi `Array Constructor` có những phương thức gì thì đối tượng được khởi tạo sẽ có 1 phương thức như vậy. Vậy nên mảng `courses` sẽ có 1 key là `forEach2`.

	Array.prototype.forEach2 = function (callback) {
		for (var index in this) {
			if (this.hasOwnProperty(index)) {
		      // check xem các key/value có nằm trong mảng đang xét hay không, loại bỏ được key forEach2
		      callback(this[index], index, this);
		   	}
		}
	};

---
## Bài 67: My filter() method
### Ví dụ:

	var courses = [
	  {
	    name: "Javascript",
	    coin: 100,
	  },
	  {
	    name: "PHP",
	    coin: 860,
	  },
	  {
	    name: "Rubby",
	    coin: 980,
	  },
	];
	
	var filterCourses = courses.filter2(function (course, index, array) {
	  return course.coin > 700;
	});
	
	console.log(filterCourses);

### Tự viết lại phương thức filer()

	Array.prototype.filter2 = function (callback) {
	  var output = []; // tạo 1 array trống
	  for (var index in this) {
	    if (this.hasOwnProperty(index)) {
	      var result = callback(this[index], index, this);
	      if (result) {
	        output.push(this[index]);
	      }
	    }
	  }
	  return output;
	};
	
---
## Bài 68: My some() method
### Ví dụ:

	var courses = [
	  {
	    name: "Javascript",
	    coin: 100,
	    isFinish: true,
	  },
	  {
	    name: "PHP",
	    coin: 860,
	    isFinish: false,
	  },
	  {
	    name: "Rubby",
	    coin: 980,
	    isFinish: false,
	  },
	];
	
	
	var result = courses.some2(function (course, index, array) {
	  return course.coin < 200;
	});
	
	console.log(result);

### Tự viết lại phương thức some()

	Array.prototype.some2 = function (callback) {
	  for (var index in this) {
	    if (this.hasOwnProperty(index)) {
	      callback(this[index], index, this);
	      return true;
	    }
	  }
	  return false;
	};

---
## Bài 69: My every() method
### Ví dụ:

	var courses = [
	  {
	    name: "Javascript",
	    coin: 100,
	    isFinish: true,
	  },
	  {
	    name: "PHP",
	    coin: 860,
	    isFinish: false,
	  },
	  {
	    name: "Rubby",
	    coin: 980,
	    isFinish: false,
	  },
	];
	
	var result = courses.every2(function (course, index, array) {
	  return course.coin < 200;
	});

### Tự viết lại phương thức every()

	Array.prototype.every2 = function (callback) {
	  var output = true;
	  for (var index in this) {
	    if (this.hasOwnProperty(index)) {
	      var result = callback(this[index], index, this);
	      if (!result) {
	        output = false;
	        break;
	      }
	    }
	  }
	  return output;
	};

---

## Bài 70: HTML DOM là gì?

 **DOM (Document Object Model)** là tiêu chuẩn giao diện lập trình ứng dụng của tổ chức W3C (World Wide Web Consortium) phân thành 3 tiêu chuẩn gồm Core DOM, XML DOM và HTML DOM.
 
**HTML DOM gồm 3 thành phần:**

1. Element: thẻ, tag
2. Attribute thuộc tính nằm trong thẻ (class, id, title, src …)
3. Text

![](https://topdev.vn/blog/wp-content/uploads/2021/01/dom-la-gi.gif)

- Mỗi ô vuông là 1 node.

- Sử dụng HTML DOM thì chúng ta có thể get, change, update, delete các thành phần của DOM.

----

## Bài 71: HTML DOM & DOM API

HTML không phải là Javascript Javascript chỉ cung cấp công cụ để chúng ta truy xuất vào HTML DOM Khi chạy trên Browser thì có DOM, vì trên Browser có WEB API, WEB API cung cấp DOM.

---

## Bài 72: Document Object

Document là đại diện cho toàn bộ website. Mỗi khi chúng ta muốn truy xuất vào từng thành phần nhỏ thì chúng ta phải đi qua đối tượng Document

---

## Bài 73: Get element methods

    <h1 class="heading">Xin chào các bạn 1</h1>
    <h1 class="heading">Xin chào các bạn 2</h1>
    <h1 class="heading">Xin chào các bạn 3</h1>
    <h1 class="heading">Xin chào các bạn 4 </h1>

    <p>Hello guys!</p>

    <div class="box">
        <h2 class="heading-2">Heading 2</h2>
        <h2 class="heading-2">Heading 2</h2>
    </div>
    <form action="" id="testForm"></form>
    <form action="" id="form-1"></form>
    <form action="" id="form-1"></form>
    <a href="" name="Youtube">My Youtube</a>

### 1. Get Element qua: ID, class, tag, CSS Selector, HTML Collection
**a) ID**

	var headingNode = document.getElementById("heading");

**b) Class**

	var headingNodes = document.getElementsByClassName("heading");

**c) Tag**

	var tagNodes = document.getElementsByTagName("p");


**d. CSS Selector**

Mặc định: Select 1 phần tử, nếu có nhiều phần tử thì select phần tử đầu tiên

	var cssNode = document.querySelector(".box .heading-2");
	
Lấy class `heading-2` đầu tiên

	var cssNode = document.querySelector(".box .heading-2:first-child");
	var cssNode = document.querySelector(".box .heading-2:nth-child(1)");

Lấy class `heading-2` thứ 2

	var cssNode = document.querySelector(".box .heading-2:nth-child(2)");

Lấy class `heading-2` cuối cùng

	var cssNode = document.querySelector(".box .heading-2:last-child");

Lấy ra `Node List`

	var cssNodes = document.querySelectorAll(".box .heading-2");

Từ `Node List` lấy ra từng class trùng tên nhau

	var cssNodes = document.querySelectorAll(".box .heading-2")[0];
	var cssNodes = document.querySelectorAll(".box .heading-2")[1];
	var cssNodes = document.querySelectorAll(".box .heading-2") .item(0);
	var cssNodes = document.querySelectorAll(".box .heading-2") .item(1);
	console.log(cssNodes[0]);
	console.log(cssNodes[1]);

**e. HTML Collection**

Lấy ra HTML Collection chứa các `form`

	console.log(document.forms);

Lấy form có ID là `testForm`

	console.log(document.forms.testForm);

Lấy form có `ID` là `form-1`, phải để trong ngoặc vuông vì `form-1` vi phạm quy tắc đặt tên biến

	console.log(document.forms["form-1"]);

Lấy ra HTML Collection chứa các thẻ `a` có attribute là `name`

	console.log(document.anchors); 

### Bài tập 1:

	<h1 class="heading">HTML DOM</h1>
	    <div class="box-1">
	        <ul>
	            <li>Javascript 1</li>
	            <li>PHP 1</li>
	        </ul>
	        <p>Test paragraph </p>
	    </div>
	    <div class="box-2">
	        <ul>
	            <li>Javascript 2</li>
	            <li>PHP 2</li>
	        </ul>
	    </div>

a) Lấy ra các thẻ `li` trong `box-1`

Cách 1:

	var listItems = document.querySelectorAll(".box-1 > ul > li");

Cách 2:

	var listItems = document.querySelectorAll(".box-1 ul li");

Cách 3:

	var boxNode = document.querySelector(".box-1");
	var listItems = boxNode.querySelectorAll("li");
	
thay vì sử dụng `querySelectorAll` thì có thể sử dụng `getElementsByTagName`

b) Lấy thẻ `<p>`

	console.log(boxNode.querySelector("p"));

### Bài tập 2:

	<div class="container">
	    <div class="box">
	        <ul>
	            <li class="item">F8 lý thuyết</li>
	            <li class="item">F8 bài tập</li>
	            <li class="item">F8 thực hành</li>
	        </ul>
	    </div>
	    <div class="box">
	        <ul>
	            <li class="item">Kiền trì</li>
	            <li class="item">Học mỗi ngày</li>
	            <li class="item">Tin vào bản thân</li>
	        </ul>
	    </div>
	</div>

a) Get elements `box` và lưu vào biến `boxHTMLCollection`

	var boxHTMLCollection = document.getElementsByClassName('box');

b) Lấy element `box` thứ nhất lưu vào biến `box1Element`

	var box1Element = document.querySelector('.container .box:nth-child(1)');

hoặc

	var box1Element = document.querySelector('.container .box:first-child');

hoặc

	var box1Element = boxHTMLCollection[0];

c) Lấy element `box` thứ hai lưu vào biến `box2Element`

	var box2Element = document.querySelector('.container .box:nth-child(2)');

hoặc

	var box2Element = document.querySelector('.container .box:last-child');

hoặc

	var box2Element = boxHTMLCollection[1];

d) Get tất cả `li` và lưu vào biến `allItemElements`

	var allItemElements = document.getElementsByTagName('li');

hoặc

	var allItemElements = document.querySelectorAll('li');

e) Get tất cả `li` là con của box thứ nhất và lưu vào biến `box1ItemElements`

	var box1ItemElements = document.querySelectorAll('.container .box:nth-child(1) li');

hoặc

	var box1ItemElements = document.querySelectorAll('.container .box:first-child li');

hoặc

	var box1ItemElements = box1Element.querySelectorAll('li');

f) Get tất cả `li` là con của box thứ hai và lưu vào biến `box2ItemElements`

	var box2ItemElements = document.querySelectorAll('.container .box:nth-child(2) li');

hoặc

	var box2ItemElements = document.querySelectorAll('.container .box:last-child li');

hoặc

	var box2ItemElements = box2Element.querySelectorAll('li');

### Bài tập 3:

	  <h1>Học lập trình tại F8</h1>
	
	  <section>
	    <h2>Học JS HTML DOM</h2>
	  </section>
	
	  <div>
	    <h3>Làm bài tập ngay trên F8</h3>
	  </div>
	  
a) Lấy `h1` element và lưu vào biến `h1Element`

	var h1Element = document.getElementsByTagName('h1').item(0);

hoặc 

	var h1Element = document.getElementsByTagName('h1')[0];
	
b) Lấy `h2` element và lưu vào biến `h2Element`

	var h2Element = document.getElementsByTagName('h2').item(0);

hoặc

	var h2Element = document.getElementsByTagName('h2')[0];

c) Lấy `h3` element và lưu vào biến `h3Element`

	var h3Element = document.getElementsByTagName('h3').item(0);

hoặc 

	var h3Element = document.getElementsByTagName('h3')[0];

### Bài tập 4:

	<div type="checkbox" value="1" name="answer"></div>
	<input type="checkbox" value="1" name="answer" />
	<input type="checkbox" value="2" name="answer" checked />
	<input type="checkbox" value="3" name="answer" disabled />
	<input type="checkbox" value="4" name="answer" checked disabled />
	
a) Get `checkbox input NodeList` lưu vào biến `checkboxNodes`

	  var checkboxNodes = document.querySelectorAll('input');

b) Get `checkbox input element` có `type="checkbox"` `value="1"` lưu vào biến `checkbox1Element`

	  var checkbox1Element = document.querySelector("input[type='checkbox'][value='1']");

c) Get `checkbox element` có `attribute checked` nhưng không có `attribute disabled` lưu vào biến `checkboxCheckedAndNotDisabled`

	  var checkboxCheckedAndNotDisabled = document.querySelector("input[checked]:not([disabled])");

d) Get `checkbox element` có `attribute disabled` nhưng không có `attribute checked` lưu vào biến `checkboxDisabledAndNotChecked`

	  var checkboxDisabledAndNotChecked = document.querySelector("input[disabled]:not([checked])");

e) Get `checkbox element` có `attribute checked` và `disabled` lưu vào biến `checkboxCheckedAndDisabled`

	  var checkboxCheckedAndDisabled = document.querySelector("input[checked][disabled]");
	
### Bài tập 5:

	  <div class="heading">
	    <div class="child">
	      <ul>
	        <li>Xin chào 1</li>
	        <li>Xin chào 2</li>
	      </ul>
	    </div>
	    <div class="child">
	      <ul>
	        <li>Xin chào 3</li>
	        <li>Xin chào 4</li>
	      </ul>
	    </div>
	  </div>
	  
Lấy ra `li` đầu tiên của class `child` đầu tiên

	  var divelement1 = document.querySelector(".heading .child:nth-child(1) ul li:nth-child(1)");

	
