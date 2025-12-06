<div align="center">

# ⚛️ Hệ Thống Kiến Thức React + Vite 🚀

[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Made with Love](https://img.shields.io/badge/Made%20with-❤️-red?style=for-the-badge)](https://github.com/NguyenLeDatToan)

---

### 👨‍💻 Người biên soạn: **Toàn Nguyễn**

</div>

---

## ⚡ Vite là gì?

> 💡 _Một công cụ build và phát triển ứng dụng web, ra đời với mục đích khắc phục những hạn chế về tốc độ và hiệu suất._

---

## 🤔 Tại sao nên sử dụng Vite?

| 🎯 Tính năng                 | 📝 Mô tả                                                                           |
| :--------------------------- | :--------------------------------------------------------------------------------- |
| 🚀 **Khởi động nhanh chóng** | Vite cho phép bạn bắt đầu dự án gần như ngay lập tức, giúp bạn tiết kiệm thời gian |
| ⚙️ **Cấu hình đơn giản**     | Được thiết kế để dễ dàng thiết lập, đặc biệt thân thiện với người mới bắt đầu      |
| 📘 **Hỗ trợ TypeScript**     | Tích hợp tốt với TypeScript, giúp viết mã nguồn an toàn và dễ bảo trì hơn          |
| ⚡ **Hiệu suất cao**         | Sử dụng ES Modules gốc và HMR, mang đến trải nghiệm phát triển mượt mà             |

---

## ⚔️ So sánh Vite vs Webpack

| 📊 Tiêu chí                  | ⚡ Vite                                                | 📦 Webpack                                    |
| :--------------------------- | :----------------------------------------------------- | :-------------------------------------------- |
| 🚀 **Tốc độ khởi động**      | ✅ Nhanh nhờ ES Modules gốc, chỉ tải các tệp cần thiết | ⏳ Chậm hơn do phải đóng gói toàn bộ mã trước |
| 🔄 **Phản hồi khi thay đổi** | ✅ HMR nhanh, mượt mà, chỉ cập nhật phần thay đổi      | ⏳ HMR khả dụng nhưng có thể chậm hơn         |
| ⚙️ **Cấu hình**              | ✅ Đơn giản, thân thiện người mới                      | ⏳ Phức tạp, cần nhiều thiết lập thủ công     |
| 🔌 **Plugin**                | ✅ API plugin mạnh mẽ, dễ tùy chỉnh                    | ⏳ Mạnh mẽ nhưng phức tạp hơn                 |
| 📦 **Kích thước build**      | ✅ Dùng Rollup, tạo file nhỏ gọn và tối ưu             | ⏳ Cần nhiều cấu hình để tối ưu               |

---

## 📚 Mục Lục

| STT | 📖 Bài học                                      | 📝 Mô tả               |
| :-: | :---------------------------------------------- | :--------------------- |
| 1️⃣  | [Cài đặt môi trường](#bài-1-cài-đặt-môi-trường) | Thiết lập React + Vite |

---

## 📘 Bài 1: Cài đặt môi trường

> 🛠️ _Dùng Vite để tạo React App_

### 1️⃣ Khởi tạo môi trường Vite

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

### 2️⃣ Cài đặt thư viện cần thiết và chạy ứng dụng

```bash
# 📦 Cài đặt các gói thư viện cần thiết
npm install

# ▶️ Chạy ứng dụng
npm run dev
```

> 💡 _Với những phiên bản mới, Vite đã tự động cài thư viện và chạy ứng dụng sau khi cài đặt rồi!_

#### ✅ Kiểm tra kết quả

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

#### 📱 Chạy trên thiết bị thật (Responsive Testing)

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

> 🌐 Truy cập bằng IP của máy tính trên cùng mạng WiFi!

### 3️⃣ Tiếp theo...

---

<div align="center">

### 🌟 Happy Coding! 🌟

⭐ **Nếu thấy hữu ích, hãy cho mình một star nhé!** ⭐

</div>
