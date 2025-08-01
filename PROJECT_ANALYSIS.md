# Phân Tích Dự Án SWP_ProjectQuitSmoking

## Tóm Tắt Dự Án (Summary)

**SWP_ProjectQuitSmoking** là một ứng dụng web hỗ trợ việc cai thuốc lá với hệ thống đa vai trò bao gồm người dùng thông thường, huấn luyện viên (coach) và quản trị viên. Ứng dụng cung cấp các tính năng theo dõi tiến trình cai thuốc, hệ thống blog, xếp hạng người dùng, thanh toán gói dịch vụ và tương tác thời gian thực giữa các bên liên quan.

### Mục Tiêu Chính:
- Hỗ trợ người dùng trong hành trình cai thuốc lá
- Kết nối người dùng với các huấn luyện viên chuyên nghiệp
- Cung cấp nền tảng quản lý toàn diện cho admin
- Tạo cộng đồng hỗ trợ qua blog và ranking system

## Trách Nhiệm Theo Vai Trò (Responsibilities)

### 👥 Người Dùng Thông Thường (User)
- **Đăng ký/Đăng nhập**: Tài khoản cá nhân với xác thực JWT và Google OAuth
- **Theo dõi tiến trình**: Ghi nhận quá trình cai thuốc hàng ngày
- **Tương tác blog**: Đọc và tham gia các bài viết về cai thuốc
- **Xem ranking**: Theo dõi bảng xếp hạng và thành tích cá nhân
- **Thanh toán dịch vụ**: Mua gói membership và dịch vụ huấn luyện
- **Nhận huy hiệu**: Đạt được các thành tích và phần thưởng
- **Tương tác với coach**: Nhận kế hoạch và hỗ trợ từ huấn luyện viên

### 🎯 Huấn Luyện Viên (Coach)
- **Quản lý thành viên**: Theo dõi danh sách và tiến trình của các học viên
- **Tạo kế hoạch**: Xây dựng kế hoạch cai thuốc cá nhân hóa
- **Tương tác trực tiếp**: Chat và tư vấn thời gian thực
- **Viết blog**: Chia sẻ kiến thức và kinh nghiệm chuyên môn
- **Quản lý profile**: Cập nhật thông tin và dịch vụ cá nhân
- **Theo dõi feedback**: Nhận và phản hồi đánh giá từ học viên

### 🛠️ Quản Trị Viên (Admin)
- **Quản lý người dùng**: Phê duyệt, khóa/mở khóa tài khoản
- **Quản lý huấn luyện viên**: Duyệt đăng ký coach, theo dõi hiệu suất
- **Quản lý nội dung**: 
  - Phê duyệt blog và danh mục blog
  - Quản lý hệ thống thông báo
  - Quản lý huy hiệu và thành tích
- **Quản lý gói dịch vụ**: Tạo và cập nhật các gói membership
- **Thống kê và báo cáo**: 
  - Doanh thu theo tháng/năm
  - Số liệu người dùng và giao dịch
  - Biểu đồ và analytics
- **Quản lý hệ thống**: Cấu hình và bảo trì tổng thể
- **Xử lý feedback**: Tiếp nhận và xử lý phản hồi từ người dùng

## Công Nghệ Sử Dụng (Technologies)

### 🎨 Frontend
- **Core Framework**: React 19.1.0 với Vite 6.3.5
- **Routing**: React Router DOM 7.6.1
- **Styling**: TailwindCSS 4.1.8
- **UI Components**: Ant Design Plots, React Icons
- **Charts & Visualization**: 
  - Chart.js 4.5.0
  - React-ChartJS-2 5.3.0
  - Recharts 3.1.0
- **Form & Date Handling**: React DatePicker 8.4.0
- **State Management**: Context API (AuthContext)

### 🔐 Authentication & Security
- **JWT Authentication**: jwt-decode 4.0.0, jwt-encode 1.0.1
- **OAuth Integration**: @react-oauth/google 0.12.2
- **HTTP Client**: Axios 1.9.0 với interceptors cho token refresh

### 💬 Real-time Communication
- **WebSocket**: @stomp/stompjs 7.1.1
- **Socket Client**: sockjs-client 1.6.1
- **Real-time Features**: Chat, notifications, live updates

### 💳 Payment Integration
- **Payment Gateway**: VNPay
- **Transaction Management**: Membership và coach payment processing

### 🛠️ Development Tools
- **Build Tool**: Vite với React plugin
- **Linting**: ESLint 9.25.0
- **Code Quality**: ESLint plugins cho React
- **Development**: Hot reload, fast refresh

### 🗄️ Backend Architecture (Inferred)
- **Main API**: ASP.NET Core (Port 5175)
- **Secondary API**: Java/Spring Boot (Port 8080) cho blog categories
- **Database**: Relational database (inferred from API structure)
- **File Storage**: Static file serving cho images/assets

### 📱 Key Features Implementation
- **Multi-role System**: Admin, Coach, User với protected routes
- **Payment Processing**: VNPay integration với callback handling
- **Blog System**: CRUD operations với approval workflow
- **Ranking System**: Badge và achievement tracking
- **Membership System**: Subscription management
- **Progress Tracking**: Daily logs và milestone tracking
- **Notification System**: Real-time alerts và updates

### 🔧 Project Structure
```
SWP_ProjectQuitSmokingg/
├── Fontend/                 # React frontend application
│   ├── src/
│   │   ├── assets/         # Admin & Coach components
│   │   ├── components/     # Shared UI components
│   │   ├── contexts/       # React contexts (Auth)
│   │   ├── pages/          # Main application pages
│   │   └── services/       # API service layers
│   ├── public/             # Static assets
│   └── package.json        # Dependencies & scripts
└── README.md               # Project documentation
```

## Đặc Điểm Nổi Bật

### 🏆 Gamification
- Hệ thống huy hiệu và thành tích
- Bảng xếp hạng cộng đồng
- Theo dõi milestone cá nhân

### 💡 Social Features
- Blog community với system phê duyệt
- Real-time messaging
- Coach-member interaction

### 📊 Analytics & Reporting
- Dashboard cho từng vai trò
- Revenue tracking và statistics
- User behavior analytics

### 🔄 Scalable Architecture
- Modular component structure
- Service-oriented API design
- Role-based access control
- Token-based authentication với refresh mechanism