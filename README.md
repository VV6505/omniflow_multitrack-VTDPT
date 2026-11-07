# OmniFlow 360 Pro — Multimodal Logistics Control Tower
> *Hệ Thống Trung Tâm Điều Hành Vận Tải Đa Phương Thức Thông Minh (VN Logistics OS v5.0)*

Xem cẩm nang hướng dẫn demo chi tiết đầy đủ tại: **[HUONG_DAN_DEMO.md](https://github.com/VV6505/omniflow_multitrack-VTDPT/blob/main/HUONG_DAN_DEMO.md)**

---

## 🚀 Khởi chạy nhanh (Quick Start)
1. Mở trực tiếp file **[`omniflow_multitrack_pro.html`](./omniflow_multitrack_pro.html)** bằng trình duyệt Google Chrome hoặc Microsoft Edge.
2. Ứng dụng chạy độc lập hoàn toàn phía Client-side (Zero-backend Standalone).
3. Không cần cài đặt `npm install` hay khởi động server phức tạp.
4. Tùy chọn: Nhập Google Gemini API Key tại Tab 6 để kích hoạt Trợ lý AI Trực tuyến siêu tốc.

---

## 📦 Cấu trúc Thư mục Dự án
```
omniflow_multitrack/
├── omniflow_multitrack_pro.html   # File ứng dụng duy nhất (Single Page Application)
├── HUONG_DAN_DEMO.md              # Cẩm nang hướng dẫn demo & tài liệu nghiệp vụ chi tiết
├── README.md                      # Tệp giới thiệu dự án
├── Phiếu B-L/                     # Thư mục lưu trữ bản gốc ảnh B/L, AWB và Tờ khai Excel
│   ├── AWB của lô 7710.jpg
│   ├── B-L của lô 3391.jpg
│   ├── Tờ-khai-SHIP-VN-8821.xlsx
│   ├── tờ khai HQ lô 7710.xls
│   ├── tờ khai HQ lô 3391.xlsx
│   └── Vận đơn của lô 9042.jpg
├── tests/                         # Bộ 9 test suites kiểm thử tự động (Node.js VM)
│   ├── goc_map.test.cjs
│   ├── dashboard_sync.test.cjs
│   ├── route_filters.test.cjs
│   ├── leg_view.test.cjs
│   ├── full_simulation.test.cjs
│   ├── pause_resume.test.cjs
│   ├── incident_replay.test.cjs
│   ├── bundled_documents.test.cjs
│   └── workflow_upgrade.test.cjs
└── src/                           # Mã nguồn module mở rộng (Workflow & Routing)
```

---

## 🛠️ Công nghệ cốt lõi
- **Giao diện:** HTML5, Tailwind CSS, FontAwesome 6, CartoDB Dark Matter.
- **Bản đồ & Định tuyến:** Leaflet.js, OSRM API, SeaRoute MARNET 20km (Chaikin 2-iteration, despur), OpenRailRouting, Great-circle spherical interpolation.
- **Mô phỏng thời gian thực:** `requestAnimationFrame`, binary search `locatePath` với cache `WeakMap`, collision detection dừng 3s khi va chạm sự cố.
- **Lưu trữ:** `IndexedDB` (`omniflow-demo-v3`), fallback `localStorage`, FNV-1a 32-bit hash, tài liệu nhúng Base64.
- **Trợ lý AI Kép (Hybrid Dual-Engine):** Google Gemini Live AI (`gemini-3.5-flash-lite`, `gemini-flash-lite-latest`, `gemini-3.1-flash-lite`, `gemini-3.8-flash`) + Offline Specialized NLP Engine.

