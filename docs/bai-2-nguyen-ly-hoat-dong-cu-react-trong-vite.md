# 📘 Bài 2: Nguyên lý hoạt động của React trong Vite

[⬅️ Quay lại Mục lục](../readme.md) | [⬅️ Bài trước](./bai-1-cai-dat-moi-truong.md)

---

> 🎯 _Hiểu cách React hoạt động bên trong môi trường Vite_

## 🏗️ Cấu trúc thư mục dự án

Khi tạo một dự án React + Vite, bạn sẽ có cấu trúc như sau:

```
📂 my-react-app/
├── 📂 node_modules/        # 📦 Thư viện đã cài đặt
├── 📂 public/              # 🌐 File tĩnh (favicon, images...)
│   └── vite.svg
├── 📂 src/                 # 💻 Source code chính
│   ├── 📂 assets/          # 🖼️ Hình ảnh, fonts...
│   │   └── react.svg
│   ├── App.css             # 🎨 Style cho App component
│   ├── App.jsx             # ⚛️ Component chính
│   ├── index.css           # 🎨 Style toàn cục
│   └── main.jsx            # 🚀 Entry point
├── .gitignore              # 🙈 File bỏ qua khi commit
├── eslint.config.js        # 🔍 Cấu hình ESLint
├── index.html              # 📄 HTML template
├── package.json            # 📋 Thông tin dự án
└── vite.config.js          # ⚙️ Cấu hình Vite
```

---

## 🔄 Luồng hoạt động của React + Vite

### 1️⃣ Entry Point: `index.html`

> 📄 _File HTML duy nhất - Single Page Application (SPA)_

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React</title>
  </head>
  <body>
    <div id="root"></div>
    <!-- 👈 React sẽ render vào đây -->
    <script type="module" src="/src/main.jsx"></script>
    <!-- 👈 Load JS -->
  </body>
</html>
```

| Thành phần               | Mô tả                                         |
| :----------------------- | :-------------------------------------------- |
| `<div id="root">`        | 🎯 Container để React render toàn bộ ứng dụng |
| `<script type="module">` | 📦 Load ES Module - Vite sử dụng native ESM   |

---

### 2️⃣ Main Entry: `main.jsx`

> 🚀 _Điểm khởi đầu của ứng dụng React_

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import "./index.css";
import App from "./App.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

| Thành phần                        | Mô tả                                         |
| :-------------------------------- | :-------------------------------------------- |
| `StrictMode`                      | 🔍 Chế độ nghiêm ngặt - phát hiện lỗi tiềm ẩn |
| `createRoot`                      | 🌳 Tạo React root (React 18+)                 |
| `document.getElementById('root')` | 🎯 Lấy element từ `index.html`                |
| `<App />`                         | ⚛️ Component gốc của ứng dụng                 |

---

### 3️⃣ App Component: `App.jsx`

> ⚛️ _Component chính - nơi xây dựng giao diện_

```jsx
import { useState } from "react";
import reactLogo from "./assets/react.svg";
import viteLogo from "/vite.svg";
import "./App.css";

function App() {
  const [count, setCount] = useState(0);

  return (
    <>
      <div>
        <a href="https://vite.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
    </>
  );
}

export default App;
```

---

## ⚡ Vite làm gì đặc biệt?

### 🔥 Hot Module Replacement (HMR)

> 💡 _Cập nhật code mà không cần reload trang_

| Tính năng              | Mô tả                                          |
| :--------------------- | :--------------------------------------------- |
| ⚡ **Instant Update**  | Thay đổi code → Cập nhật ngay lập tức          |
| 🔄 **State Preserved** | Giữ nguyên state khi update                    |
| 🎯 **Partial Update**  | Chỉ update phần thay đổi, không reload toàn bộ |

### 📦 ES Modules Native

```javascript
// Vite sử dụng ES Modules gốc của trình duyệt
import { useState } from "react"; // 👈 Native import
```

| So sánh | Webpack                | Vite                    |
| :------ | :--------------------- | :---------------------- |
| Bundle  | ✅ Bundle tất cả trước | ❌ Không bundle khi dev |
| Load    | 📦 Load 1 file lớn     | 📂 Load từng module     |
| Tốc độ  | ⏳ Chậm khi dự án lớn  | ⚡ Nhanh luôn           |

---

## 🎨 CSS trong Vite

### Import CSS trực tiếp

```jsx
import "./App.css"; // 👈 Import CSS vào component
```

### CSS Modules (tùy chọn)

```jsx
import styles from "./App.module.css";

function App() {
  return <div className={styles.container}>Hello</div>;
}
```

---

## 📝 Tóm tắt luồng hoạt động

```
┌─────────────────────────────────────────────────────────────┐
│  1. Browser request → index.html                            │
│  2. index.html load → main.jsx (ES Module)                  │
│  3. main.jsx import → App.jsx + CSS                         │
│  4. createRoot() → Render <App /> vào #root                 │
│  5. Vite HMR → Watch changes → Update instantly             │
└─────────────────────────────────────────────────────────────┘
```

---

<div align="center">

[⬅️ Bài trước: Cài đặt môi trường](./bai-1-cai-dat-moi-truong.md) | [➡️ Bài tiếp theo](./bai-3-coming-soon.md)

[⬅️ Quay lại Mục lục](../readme.md)

</div>
