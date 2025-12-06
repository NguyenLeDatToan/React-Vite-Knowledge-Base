# 📘 Bài 1: Cài đặt môi trường

[⬅️ Quay lại Mục lục](../readme.md)

---

> 🛠️ _Dùng Vite để tạo React App_

## 1️⃣ Khởi tạo môi trường Vite

> 📦 _Vite sẽ làm môi trường cho React App bên trong nó hoạt động_

Chọn một trong các package manager sau:

```bash
# 📦 npm
npm create vite@[version]

# 🧶 yarn
yarn create vite@[version]

# 🚀 pnpm
pnpm create vite@[version]

# 🍞 bun
bun create vite@[version]
```

> 💡 **Ví dụ:** `npm create vite@latest` → Phiên bản mới nhất

---

## 2️⃣ Cài đặt thư viện cần thiết và chạy ứng dụng

```bash
# 📦 Cài đặt các gói thư viện cần thiết
npm install

# ▶️ Chạy ứng dụng
npm run dev
```

> 💡 _Với những phiên bản mới, Vite đã tự động cài thư viện và chạy ứng dụng sau khi cài đặt rồi!_

### ✅ Kiểm tra kết quả

- 🌐 Mở trình duyệt và truy cập: **http://localhost:5173/**
- 🔌 Port mặc định là `5173`, nhưng có thể thay đổi trong `vite.config.js`:

```javascript
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

// https://vite.dev/config/
export default defineConfig({
  plugins: [react()],
  server: {
    port: 11000, // 👈 Thay đổi port tại đây
  },
});
```

### 📱 Chạy trên thiết bị thật (Responsive Testing)

> 💡 _Khi muốn test responsive trên các thiết bị thật (điện thoại, tablet,...)_

Thay đổi trong file `package.json`:

```json
{
  "scripts": {
    "dev": "vite --host" // 👈 Thêm --host để mở network access
  }
}
```

Sau đó chạy lại:

```bash
npm run dev
```

> 🌐 Truy cập bằng IP:PORT của máy tính trên cùng mạng WiFi!

---

## 3️⃣ Xây dựng cho Sản xuất (Production Build)

> 🏭 _Tạo bản build tối ưu để deploy lên server_

```bash
# 📦 Build ứng dụng
npm run build
```

> ✅ Vite sẽ tạo thư mục `dist/` chứa các file đã được tối ưu hoá

### 👀 Xem trước bản build

```bash
# 🔍 Preview bản production
npm run preview
```

> 🌐 Server preview chạy tại: **http://localhost:4173/**

---

<div align="center">

[⬅️ Quay lại Mục lục](../readme.md) | [➡️ Bài tiếp theo: Nguyên lý hoạt động](./bai-2-nguyen-ly-hoat-dong-cu-react-trong-vite.md)

</div>
