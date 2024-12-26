# Hướng dẫn Deploy

Đây là cú pháp Markdown.

## Tách riêng 2 project

- backend:
- frontend:

## Backend

Chạy lệnh này trước: `npm init` sẽ tự động tạo tệp package.json => Gõ enter nhiều lần xong yes

- Cài các thư viện sau:

```shell
npm i cors
npm i json-server@0.17.1
```

Chạy các lệnh trên nó sẽ tự tạo ra thư mục node_modules.

Tạo file .gitignore trước, bên trong để là:

```
node_modules
```

Tạo một tệp `index.js` với nội dung như sau:

```
const jsonServer = require("json-server"); // importing json-server library
const server = jsonServer.create();
const router = jsonServer.router("db.json");
const middlewares = jsonServer.defaults();
const port = process.env.PORT || 3001; // you can use any port number here; i choose to use 3001

server.use(middlewares);
server.use(router);

server.listen(port);
```

Copy file `db.json` vào thư mục dự án backend hoặc paste mã sau:

```json
{
	"information": [
		{
			"stt": 1,
			"id": 1,
			"name": "Nguyễn Thị A",
			"gender": "Female",
			"phone": "0123456789",
			"addressId": 3,
			"email": "nguyenthia@gmail.com"
		},
		{
			"stt": 2,
			"id": 2,
			"name": "Trần Văn B",
			"gender": "Male",
			"phone": "0987654321",
			"addressId": 2,
			"email": "tranvanb@gmail.com"
		},
		{
			"stt": 3,
			"id": 3,
			"name": "Nguyễn Văn C",
			"gender": "Male",
			"phone": "0192837465",
			"addressId": 1,
			"email": "nguyenvanc@gmail.com"
		},
		{
			"id": "4",
			"name": "Thanh Hang",
			"gender": "Female",
			"phone": "0374926592",
			"email": "dinhhang440@gmail.com",
			"addressId": "1"
		},
		{
			"id": "5",
			"name": "Huyen Tran",
			"gender": "Female",
			"phone": "0977659041",
			"email": "tran.htran6123@gmail.com",
			"addressId": "1"
		}
	],
	"addresses": [
		{
			"id": 1,
			"name": "Ha Noi"
		},
		{
			"id": 2,
			"name": "TP Ho Chi Minh"
		},
		{
			"id": 3,
			"name": "Da Nang"
		}
	]
}
```

- Trên trang Github.com tạo repo mới tên là `backend`, liên kết thư mục `backend` này với repo vừa tạo chứ không phải thư mục deploy, thư mục deploy chỉ quản lý trong máy tính mình thôi.

## Frontend
