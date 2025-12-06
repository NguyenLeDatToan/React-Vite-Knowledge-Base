# 📘 Bài 3: Tạo một thành phần mới trong React (Component)

[⬅️ Quay lại Mục lục](../readme.md) | [⬅️ Bài trước](./bai-2-nguyen-ly-hoat-dong-cu-react-trong-vite.md)

---

> 🎯 _Học cách tạo và sử dụng Component - khối xây dựng cơ bản của React_

## 🧩 Component là gì?

> 💡 _Component là một khối giao diện độc lập, có thể tái sử dụng_

| Đặc điểm           | Mô tả                                        |
| :----------------- | :------------------------------------------- |
| 🔄 **Tái sử dụng** | Viết một lần, dùng nhiều nơi                 |
| 📦 **Độc lập**     | Mỗi component quản lý logic riêng            |
| 🧱 **Kết hợp**     | Ghép nhiều component nhỏ thành component lớn |
| 🎨 **Dễ bảo trì**  | Sửa một chỗ, cập nhật mọi nơi                |

---

## 📁 Cấu trúc thư mục khuyến nghị

```
📂 src/
├── 📂 components/          # 🧩 Chứa các component
│   ├── CreateAComponent.jsx
│   ├── Header.jsx
│   └── Footer.jsx
├── App.jsx                 # ⚛️ Component gốc
└── main.jsx                # 🚀 Entry point
```

> 💡 **Tip:** Đặt mỗi component trong một file riêng để dễ quản lý!

---

## 🛠️ Cách tạo một Component

### 1️⃣ Tạo file Component

Tạo file `src/components/CreateAComponent.jsx`:

```jsx
function CreateAComponent() {
  return <h1>Hello</h1>;
}

export default CreateAComponent;
```

| Thành phần                    | Mô tả                                   |
| :---------------------------- | :-------------------------------------- |
| `function CreateAComponent()` | 📝 Khai báo function component          |
| `return <h1>Hello</h1>`       | 🎨 Trả về JSX (giao diện)               |
| `export default`              | 📤 Xuất component để sử dụng ở nơi khác |

---

### 2️⃣ Import và sử dụng Component

Trong file `App.jsx`:

```jsx
import CreateAComponent from "./components/CreateAComponent.jsx";

function App() {
  return (
    <div>
      <CreateAComponent />
    </div>
  );
}

export default App;
```

| Thành phần                           | Mô tả                                 |
| :----------------------------------- | :------------------------------------ |
| `import CreateAComponent from "..."` | 📥 Import component đã tạo            |
| `<CreateAComponent />`               | 🧩 Sử dụng component như một thẻ HTML |

---

## 📐 Quy tắc đặt tên Component

| Quy tắc              | Ví dụ                   | Mô tả                       |
| :------------------- | :---------------------- | :-------------------------- |
| ✅ **PascalCase**    | `CreateAComponent`      | Viết hoa chữ cái đầu mỗi từ |
| ✅ **Mô tả rõ ràng** | `UserProfile`, `NavBar` | Tên phản ánh chức năng      |
| ❌ **camelCase**     | `createAComponent`      | ❌ Không dùng cho component |
| ❌ **snake_case**    | `create_a_component`    | ❌ Không dùng cho component |

> ⚠️ **Quan trọng:** React phân biệt component (viết hoa) và thẻ HTML (viết thường)

```jsx
// ✅ Đúng - React hiểu đây là component
<CreateAComponent />

// ❌ Sai - React hiểu đây là thẻ HTML
<createacomponent />
```

---

## 🔄 Luồng hoạt động

```
┌─────────────────────────────────────────────────────────────┐
│  1. main.jsx render <App />                                 │
│  2. App.jsx import CreateAComponent                         │
│  3. App.jsx render <CreateAComponent />                     │
│  4. CreateAComponent trả về <h1>Hello</h1>                  │
│  5. Kết quả: <div><h1>Hello</h1></div>                      │
└─────────────────────────────────────────────────────────────┘
```

---

## 🎯 Ví dụ thực tế: Tạo nhiều Component

### Header Component

```jsx
// src/components/Header.jsx
function Header() {
  return (
    <header>
      <h1>🚀 My React App</h1>
      <nav>
        <a href="/">Home</a>
        <a href="/about">About</a>
      </nav>
    </header>
  );
}

export default Header;
```

### Footer Component

```jsx
// src/components/Footer.jsx
function Footer() {
  return (
    <footer>
      <p>© 2025 - Made with ❤️ by Toàn Nguyễn</p>
    </footer>
  );
}

export default Footer;
```

### Kết hợp trong App.jsx

```jsx
import Header from "./components/Header.jsx";
import CreateAComponent from "./components/CreateAComponent.jsx";
import Footer from "./components/Footer.jsx";

function App() {
  return (
    <div>
      <Header />
      <main>
        <CreateAComponent />
      </main>
      <Footer />
    </div>
  );
}

export default App;
```

---

## 📝 Tóm tắt

| Bước | Hành động                                 |
| :--- | :---------------------------------------- |
| 1️⃣   | Tạo file `.jsx` trong `src/components/`   |
| 2️⃣   | Viết function component với `return` JSX  |
| 3️⃣   | `export default` component                |
| 4️⃣   | `import` component vào file cần dùng      |
| 5️⃣   | Sử dụng như thẻ HTML: `<ComponentName />` |

---

## 💡 Tip: Extensions hữu ích cho React Development

### 🎨 Prettier - Code formatter

> Extension hỗ trợ tự động format code khi save, giúp code luôn gọn gàng và nhất quán!

| Tính năng               | Mô tả                                    |
| :---------------------- | :--------------------------------------- |
| ⚡ **Auto Format**      | Tự động sắp xếp code khi lưu file        |
| 📐 **Consistent Style** | Đảm bảo code style nhất quán trong dự án |
| 🔧 **Dễ cấu hình**      | Tùy chỉnh theo ý muốn qua `.prettierrc`  |

---

### ⚛️ ES7+ React/Redux/React-Native snippets

> Snippets giúp viết code React nhanh hơn với các shortcut!

| Shortcut    | Kết quả                               |
| :---------- | :------------------------------------ |
| `rafce`     | React Arrow Function Component Export |
| `rfc`       | React Function Component              |
| `useState`  | useState Hook snippet                 |
| `useEffect` | useEffect Hook snippet                |

---

### 🔍 ESLint

> Phát hiện lỗi và cảnh báo trong code JavaScript/React

| Tính năng              | Mô tả                         |
| :--------------------- | :---------------------------- |
| 🐛 **Error Detection** | Phát hiện lỗi syntax và logic |
| ⚠️ **Warnings**        | Cảnh báo code không tối ưu    |
| 🔧 **Auto Fix**        | Tự động sửa một số lỗi        |

---

### 🏷️ Auto Rename Tag

> Tự động đổi tên thẻ đóng khi sửa thẻ mở (và ngược lại)

```jsx
// Khi sửa <div> thành <section>
// Thẻ </div> tự động đổi thành </section>
<section>
  <h1>Hello</h1>
</section>
```

---

### 🌈 Bracket Pair Colorizer (Built-in VS Code)

> Tô màu các cặp ngoặc để dễ nhìn hơn

| Tính năng             | Mô tả                            |
| :-------------------- | :------------------------------- |
| 🎨 **Color Matching** | Mỗi cặp ngoặc một màu khác nhau  |
| 👁️ **Easy Reading**   | Dễ dàng nhận biết scope của code |

---

### 📁 Simple React Snippets

> Snippets đơn giản và nhẹ cho React

| Shortcut | Kết quả                                   |
| :------- | :---------------------------------------- |
| `imr`    | `import React from 'react'`               |
| `imrs`   | `import React, { useState } from 'react'` |
| `cc`     | Class Component                           |
| `fc`     | Function Component                        |

---

### 📊 Tổng hợp Extensions nên cài

| Extension                    | Mô tả               | Độ ưu tiên       |
| :--------------------------- | :------------------ | :--------------- |
| 🎨 **Prettier**              | Format code tự động | ⭐⭐⭐ Bắt buộc  |
| ⚛️ **ES7+ React Snippets**   | Snippets cho React  | ⭐⭐⭐ Bắt buộc  |
| 🔍 **ESLint**                | Phát hiện lỗi       | ⭐⭐⭐ Bắt buộc  |
| 🏷️ **Auto Rename Tag**       | Đổi tên thẻ tự động | ⭐⭐ Khuyên dùng |
| 📁 **Simple React Snippets** | Snippets bổ sung    | ⭐ Tùy chọn      |

> 💡 **Tip:** Sau khi cài Prettier, thêm vào `settings.json`:
>
> ```json
> {
>   "editor.formatOnSave": true,
>   "editor.defaultFormatter": "esbenp.prettier-vscode"
> }
> ```

---

<div align="center">

[⬅️ Bài trước: Nguyên lý hoạt động](./bai-2-nguyen-ly-hoat-dong-cu-react-trong-vite.md) | [➡️ Bài tiếp theo](./bai-4-coming-soon.md)

[⬅️ Quay lại Mục lục](../readme.md)

</div>
