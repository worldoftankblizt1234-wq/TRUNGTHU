# 🌕 Đêm Hội Trăng Rằm - Minigame Trung Thu

> Minigame đố vui tương tác realtime dành cho lớp học, tổ chức trò chơi Trung thu kết hợp kiến thức và phần thưởng blindbox.

---

## 📖 Giới thiệu

Đây là dự án minigame Trung thu được thiết kế cho hoạt động lớp học. Hệ thống gồm 2 thành phần chính:

- **Host Controller**: Trang điều khiển dành cho người dẫn chương trình (Host), quản lý câu hỏi, phần thưởng, âm thanh và trạng thái màn hình.
- **TV Screen**: Màn hình trình chiếu dành cho khán giả, nhận dữ liệu realtime từ Host qua Firebase.

Minigame bao gồm **42 câu hỏi** về chủ đề Trung thu (văn hóa, lịch sử, khoa học tự nhiên), kết hợp hệ thống **blindbox bốc quà** với tỷ lệ ngẫu nhiên và cơ chế trừ lượt thông minh.

---

## ✨ Tính năng

### 🎮 Gameplay
- **42 câu hỏi** đa dạng chủ đề: văn hóa, lịch sử, hóa học, vật lý, nghệ thuật.
- **Đồng bộ realtime** giữa Host và TV qua Firebase Realtime Database.
- **Timer đếm ngược** có thể tùy chỉnh (mặc định 15 giây).
- **Highlight đáp án** đúng/sai với hiệu ứng màu sắc.
- **Confetti** khi Host trả lời đúng.
- **Blindbox 3 hộp** với tỷ lệ phần thưởng tùy chỉnh.

### 🎁 Hệ thống phần thưởng
- **Quản lý phần thưởng** qua Prize Manager: tên quà, tỷ lệ %, số lượt, số trừ mỗi lần bốc.
- **Cơ chế trừ lượt**: mỗi lần bốc trúng sẽ trừ số lượt tương ứng khỏi quà.
- **Popup thông báo** "Phần quà đã hết" hiện giữa màn hình TV.
- **Backup prize pool**: reset phòng sẽ khôi phục số lượt ban đầu.
- **Hộp rỗng**: khi hết quà, hộp hiển thị "Chúc may mắn lần sau 🍀".

### 🎵 Âm thanh
- **3 track nhạc** độc lập:
  - `music.mp3` - Nhạc Lobby (màn hình chờ)
  - `music1.mp3` - Nhạc câu hỏi (volume 78%)
  - `music2.mp3` - Nhạc Outro (volume 65%)
- **Điều khiển từ Host**: bật/tắt và âm lượng riêng cho từng track.
- **Không chồng nhạc**: tự động tắt nhạc không phù hợp khi chuyển mode.
- **Web Audio API**: phát mượt, không khựng.

### 🖥️ Màn hình
- **3 layer** độc lập: Lobby, Game, Outro.
- **Chuyển màn hình** với hiệu ứng fade in/out 1 giây.
- **Responsive** trên mobile và TV.
- **Watermark** đa lớp bảo vệ bản quyền (canvas + pseudo-element + MutationObserver).
- **Font hỗ trợ** ký tự đặc biệt (subscript hóa học).

---

## 🛠️ Công nghệ sử dụng

| Thành phần | Công nghệ |
|---|---|
| **Frontend** | HTML5, CSS3, JavaScript (ES Modules) |
| **Styling** | Tailwind CSS (CDN) |
| **Backend** | Cloudflare Workers (API câu hỏi) |
| **Database** | Firebase Realtime Database |
| **Hosting** | Cloudflare Pages |
| **Audio** | Web Audio API |
| **Effects** | Canvas Confetti, Font Awesome |
| **Fonts** | Google Fonts (Montserrat, Playfair Display, Noto Sans) |

---

## 📁 Cấu trúc dự án
TRUNGTHU/
├── index.html # TV Screen - Màn hình trình chiếu
├── host.html # Host Controller - Trang điều khiển
├── music.mp3 # Nhạc Lobby
├── music1.mp3 # Nhạc câu hỏi
├── music2.mp3 # Nhạc Outro
└── README.md # File này


## 👥 Tác giả

**Tổ 4** — Thiết kế & Lập trình: Minh

---

© Product of Minh
