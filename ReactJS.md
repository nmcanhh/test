# ReactJS

Mẫu file component `.js`

![](https://i.ibb.co/0BMZPFt/code.png)

### 0) Vị trí viết 

a) Khai báo biến, đối tượng

Viết `trên return()`

b) Định nghĩa function

Viết `trên render()`

c) JSX, hiển thị biến, function

Viết `trong return()`

### 1) Sử dụng câu điều kiện để hiển thị

a) Toán tử 3 ngôi

Khởi tạo đối tượng:

	var product = {
	      id: 1,
	      name: "Iphone 7+",
	      price: 20000,
	      status: true,
	    };

Show dữ liệu:

	Status: {product.status ? "Active" : "Pending"}

`status == true` thì cho ra Active, `status == false` thì cho ra Pending 

b) Câu điều kiện If 

Định nghĩa function:

	  showInfoProduct(product) {
	    if (product.status) {
	      return (
	        <h3>
	          ID: {product.id} <br />
	          Name: {product.name} <br />
	          Price: {product.price} <br />
	          Status: {product.status ? "Active" : "Pending"} <br />
	        </h3>
	      );
	    }
	  }

Show dữ liệu:
	
	{this.showInfoProduct(product)}
	
### 2) Hiển thị danh sách các đối tượng: sử dụng hàm map()

Khởi tạo mảng:

    var users = [
      {
        id: 1,
        name: "Nguyen Van A",
        age: 18,
      },
      {
        id: 2,
        name: "Nguyen Van B",
        age: 18,
      },
      {
        id: 3,
        name: "Nguyen Van C",
        age: 18,
      },
    ];

Sử dụng hàm map() để render ra dữ liệu

    var elements = users.map((user, index) => {
      return (
        <div key={user.id}>
          <h2>Tên: {user.name}</h2>
          <p>Tuổi: {user.age}</p>
        </div>
      );
    });
 
Ở thẻ `div` phải có thuộc tính `key` là unique, có thể dùng id của object hoặc index. Nếu không có `key` thì sẽ báo lỗi.

Show dữ liệu:

	{elements}
	
### 3) Props

Props là các thuộc tính của 1 component, component có thể xem như là class. 

**a) Sử dụng `this.props.key` để lấy dữ liệu từ class cha về class con**

Chúng ta sử dụng props **để truyền dữ liệu** từ class cha sang class con.

Ví dụ, Product1.js nằm trong App.js thì Product là class con của App.

Tại App.js, `import Product from "./components/Product"`

Bên trong thẻ `Product`, ta truyền vào 2 key là `name` và `price`. Value nhận vào sẽ có kiểu dữ liệu là chuỗi. Muốn hiện đúng kiểu dữ liệu thì sử dụng `{}`

App.js

        <div className="container">
          <div className="row">
            <div className="row">
              <div className="col-xs-12 col-sm-12 col-md-12 col-lg-12">
                <Product name="Iphone 6S Plus" price="15000000 " />
              </div>
            </div>
          </div>
        </div>

Tại Product1.js, sử dụng this.props.`tên_key_ở_class_cha`
	
	  <h3>{this.props.name}</h3>
	  <p>{this.props.price} VNĐ</p>

Vì vậy, không được đặt key là `children`, sẽ bị trùng với trường hợp bên dưới.

**b) Sử dụng `this.props.children` để lấy nội dung trong cặp thẻ của ở class cha về class con**

Tại App.js, thay vì sử dụng `<Product1 />` thì chúng ta sử dụng `<Product1></Product1>` để truyền nội dung vào ở giữa.


	<Product price="15000000" image="https://cdn.tgdd.vn/Products/Images/42/87846/iphone-6s-plus-32gb-hh-600x600-600x600-600x600-600x600.jpg">Iphone 6S Plus</Product>
	



Tại Product1.js 

	<h3>{this.props.children}</h3>



**c) Sử dụng map() render mảng, sử dụng điều kiện để hiển thị từng object của mảng.**

Tại App.js, khởi tại mảng `products`

	var products = [
	      {
	        id: 1,
	        name: "Iphone 6S Plus",
	        price: 0,
	        image:
	          "https://cdn.tgdd.vn/Products/Images/42/87846/iphone-6s-plus-32gb-hh-600x600-600x600-600x600-600x600.jpg",
	        status: true,
	      },
	      {
	        id: 2,
	        name: "Iphone 7 Plus",
	        price: 0,
	        image:
	          "https://cdn.tgdd.vn/Products/Images/42/87846/iphone-6s-plus-32gb-hh-600x600-600x600-600x600-600x600.jpg",
	        status: false,
	      },
	      {
	        id: 3,
	        name: "Iphone 8 Plus",
	        price: 0,
	        image:
	          "https://cdn.tgdd.vn/Products/Images/42/87846/iphone-6s-plus-32gb-hh-600x600-600x600-600x600-600x600.jpg",
	        status: false,
	      },
	    ];

Khởi tại biến `elements` sử dụng map() để render mảng.

    let elements = products.map((product, index) => {
      let result = "";
      if (product.status) {
        result = (
          <Product2
            key={product.id}
            price={product.price} 
            image={product.image}
          >
            {product.name}
          </Product2>
        );
      }
      return result;
    });

Gọi `elements` tại App.js
	
	{elements}

Tại Product2.js

	<img src={this.props.image} alt={this.props.name} />
	<div className="caption">
	  <h3>{this.props.children}</h3>
	  <p>{this.props.price} VNĐ</p>
	  <p>
	    <a className="btn btn-success">Mua ngay</a>
	  </p>
	</div>

### 4) Xử lý sự kiện

Có 2 cách, chỉ sử dụng ES6. Dùng để bắt sự kiện các button, input, select: onClick,...

Tìm hiểu thêm về các sự kiện [tại đây](https://reactjs.org/docs/events.html#gatsby-focus-wrapper)

### Khai báo function ES6 

a) Không có tham số, gọi thông qua tên function

Định nghĩa function:

	onClick() {
	    alert("Xin chào");
	  }

Gọi function:

	<button type="button" className="btn btn-warning" onClick={this.onClick}>
		Click me
	</button>

b) Có tham số, gọi thông qua arrow function: `{() => this.onClick(params)}`

Định nghĩa function:

	onAddtoCart(text) {
    alert(text);
  }

Gọi function:

	<a className="btn btn-success" onClick={() => { this.onAddtoCart("Mua thành công") }} >
	Mua ngay
	</a>

c) Gọi và sử dụng props 

- Cách 1:

	Tạo constructor có tham số `props` và gọi `super(props)`. Khai báo **this.tên-function = this.tên-function.bind(this)** trong constructor.
	
		constructor(props) {
			super(props);
			this.onAddtoCart = this.onAddtoCart.bind(this);
		}

	Định nghĩa function
	
		onAddtoCart() {
	    alert(this.props.children);
	  	}
	
	Tại JSX, gọi **this.tên_function** trong thuộc tính **onClick**
	
		<a className="btn btn-success" onClick={this.onAddtoCart}>
		Mua ngay
		</a>
	
	Chúng ta cũng có thể truyền nhiều props trong function
	
		onAddtoCart() {
	    alert(this.props.children + " - " + this.props.price);
	  	}

- Cách 2

	Định nghĩa function sử dụng Arrow function
	
		onAddtoCart2 = () => {
	    alert(this.props.children + " - " + this.props.price);
	  	};
	  
	 Tại JSX, gọi **this.tên_function** trong thuộc tính **onClick**
	
		<a className="btn btn-success" onClick={this.onAddtoCart}>
		Mua ngay
		</a>

### 4) Refs

Refs dùng để lấy giá trị các ô input, textarea,...

Tìm hiểu thêm [tại đây](https://reactjs.org/docs/refs-and-the-dom.html#gatsby-focus-wrapper)

- Cách 1:

	Tạo constructor có tham số `props` và gọi `super(props)`. Khai báo **this.tên-function = this.tên-	function.bind(this)** trong constructor.
	
		constructor(props) {
	    super(props);
	    this.onAddProduct = this.onAddProduct.bind(this);
	  	}

	Định nghĩa function
	
		onAddProduct() {
	    	console.log(this.refs.name.value);
	  	}
	
	Tại JSX, gọi **this.tên_function** trong thuộc tính **onClick**
	
		<a className="btn btn-success" onClick={this.onAddProduct}>
		Mua ngay
		</a>

- Cách 2:

	Định nghĩa function sử dụng Arrow function
	
		onAddProduct = () => {
		console.log(this.refs.name.value);
		};
	  
	Tại JSX, gọi **this.tên_function** trong thuộc tính **onClick**
	
		<a className="btn btn-success" onClick={this.onAddProduct}>
		Mua ngay
		</a>

### 5) State

State là trạng thái của component, dùng để khai báo những giá trị cần lưu trữ của riêng component đó.

Tạo state tại constructor bằng cách gọi **this.state = {key1: value1, key2: value2,...}**

	  constructor(props) {
	    super(props);
	    this.state = {
	      products: [
	        {
	          id: 1,
	          name: "Iphone 6S Plus",
	          price: 6500000,
	          image:
	            "https://cdn.tgdd.vn/Products/Images/42/87846/iphone-6s-plus-32gb-hh-600x600-600x600-600x600-600x600.jpg",
	          status: true,
	        },
	        {
	          id: 2,
	          name: "Iphone 7 Plus",
	          price: 8200000,
	          image:
	            "https://cdn.tgdd.vn/Products/Images/42/87846/iphone-6s-plus-32gb-hh-600x600-600x600-600x600-600x600.jpg",
	          status: true,
	        },
	        {
	          id: 3,
	          name: "Iphone 8 Plus",
	          price: 9500000,
	          image:
	            "https://cdn.tgdd.vn/Products/Images/42/87846/iphone-6s-plus-32gb-hh-600x600-600x600-600x600-600x600.jpg",
	          status: true,
	        },
	      ],
	      isActive: true,
	    };
	  }
 
Sử dụng map() để render dữ liệu, gọi từ `this.state.products` thay vì gọi `products` như bình thường.

    let elements = this.state.products.map((product, index) => {
      let result = "";
      if (product.status) {
        result = (
          <tr key={index}>
            <td>{index}</td>
            <td>{product.name}</td>
            <td>
              <span className="label label-success">{product.price}</span>
            </td>
          </tr>
        );
      }
      return result;
    }); 

Tạo bảng để hiển thị dữ liệu, tạo 1 button hiển thị trạng thái của `isActive`, sử dụng thuộc tính onClick để bắt sự kiện `onSetSate`

    <div className="container">
      <div className="row">
        <div className="row">
          <table className="table table-bordered table-hover">
            <thead>
              <tr>
                <th>STT</th>
                <th>Tên sản phẩm</th>
                <th>Giá</th>
              </tr>
            </thead>
            <tbody>{elements}</tbody>
          </table>
          <button
            type="button"
            className="btn btn-lg btn-warning"
            onClick={this.onSetState}
          >
            Active : {this.state.isActive === true ? "true" : "false"}
          </button>
        </div>
      </div>
    </div>

Định nghĩa function `onSetState`

	  onSetState = () => {
		if (this.state.isActive === true) {
			this.setState({ isActive: false });
		} else {
			this.setState({ isActive: true });
		}
	  };

Chúng ta cũng có thể viết ngắn gọn như sau:

	  onSetState = () => {
	    this.setState({
	      isActive: !this.state.isActive,
	    });
	  };