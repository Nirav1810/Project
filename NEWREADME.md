# Attendance Management System

A comprehensive attendance management system built with React.js (teacher frontend), React Native (student mobile app), and Node.js/Express backend, featuring QR code-based attendance tracking, face verification, and real-time reporting.

## 🌟 Key Features

### For Teachers
- **Dashboard Analytics**: Real-time attendance statistics and trends
- **QR Code Management**: Generate, refresh, and terminate dynamic QR sessions
- **Manual Attendance**: Mark attendance manually for students
- **Class Management**: Create and manage classes with student enrollments
- **Schedule Management**: Set up class schedules with recurring patterns
- **Attendance Reports**: Detailed reports with export options (PDF/CSV)
- **Student Management**: View and manage students in classes

### For Students
- **QR Code Scanning**: Scan teacher-generated QR codes to mark attendance
- **Face Verification**: Biometric verification during attendance marking
- **Attendance History**: View personal attendance records
- **Class Enrollment**: Access enrolled classes and schedules
- **Real-time Updates**: Instant feedback on attendance status

### Security & Access
- **Role-based Authentication**: JWT-based authentication with role separation
- **Data Isolation**: Teacher data isolation ensuring privacy
- **Secure API**: Protected endpoints with middleware validation
- **Face Biometrics**: Liveness detection to prevent fraud

## 🏗️ Technology Stack

### Backend (attendence-backend)
- **Node.js v24.4.0** (ESM modules)
- **Express.js**: RESTful API framework
- **MongoDB**: NoSQL database with Mongoose ODM
- **JWT**: Secure authentication
- **Bcrypt**: Password hashing
- **CORS**: Cross-origin resource sharing

### Teacher Frontend (teacher-frontend)
- **React 19.1.1**: Modern React with hooks
- **Tailwind CSS**: Utility-first styling
- **React Query**: Server state management
- **React Router**: Client-side routing
- **Axios**: HTTP client
- **Chart.js**: Data visualization
- **jsPDF**: PDF report generation

### Student Mobile App (qr-student-app)
- **React Native**: Cross-platform mobile development
- **Expo**: Development framework
- **React Navigation**: Mobile navigation
- **Vision Camera**: Camera functionality
- **ML Kit**: Face detection and verification
- **QR Code Scanner**: Barcode scanning
- **Axios**: HTTP client

## 📁 Project Structure

```
attendenceapp/
├── attendence-backend/          # Backend API server
│   ├── src/
│   │   ├── shared/             # Shared components (models, controllers, routes)
│   │   ├── student/            # Student-specific components
│   │   ├── teacher/            # Teacher-specific components
│   │   └── index.js            # Shared exports
│   ├── server.js               # Entry point
│   └── package.json
├── teacher-frontend/           # Teacher web dashboard
│   ├── src/
│   │   ├── components/         # Reusable UI components
│   │   ├── pages/              # Page components
│   │   ├── services/           # API service layer
│   │   ├── contexts/           # React contexts
│   │   ├── hooks/              # Custom hooks
│   │   └── utils/              # Utility functions
│   └── package.json
├── qr-student-app/             # Student mobile application
│   ├── src/
│   │   ├── components/         # UI components
│   │   ├── screens/            # Screen components
│   │   ├── services/           # API service layer
│   │   ├── contexts/           # React contexts
│   │   ├── hooks/              # Custom hooks
│   │   ├── navigation/         # App navigation
│   │   └── utils/              # Utility functions
│   └── package.json
└── README.md
```

## 🚀 Setup Instructions

### Prerequisites
- Node.js (v24.4.0 or higher)
- MongoDB database
- Expo CLI (for mobile app development)
- npm or yarn package manager

### Backend Setup
1. Navigate to the backend directory:
   ```bash
   cd attendence-backend
   ```

2. Install dependencies:
   ```bash
   yarn install
   ```

3. Create a `.env` file with the following variables:
   ```env
   PORT=5001
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   ```

4. Start the server:
   ```bash
   yarn start
   ```

### Teacher Frontend Setup
1. Navigate to the frontend directory:
   ```bash
   cd teacher-frontend
   ```

2. Install dependencies:
   ```bash
   yarn install
   ```

3. Create a `.env` file with the backend URL:
   ```env
   REACT_APP_API_URL=http://localhost:5001/api
   ```

4. Start the development server:
   ```bash
   yarn start
   ```

### Student Mobile App Setup
1. Navigate to the mobile app directory:
   ```bash
   cd qr-student-app
   ```

2. Install dependencies:
   ```bash
   yarn install
   ```

3. Create a `.env` file with the backend URL:
   ```env
   API_URL=http://192.168.1.x:5001/api  # Replace with your machine's IP
   ```

4. Start the Expo development server:
   ```bash
   npx expo start
   ```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile

### Classes
- `GET /api/classes` - Get user's classes
- `POST /api/classes` - Create new class
- `GET /api/classes/:id` - Get specific class
- `PUT /api/classes/:id` - Update class
- `DELETE /api/classes/:id` - Delete class

### Attendance
- `POST /api/attendance` - Submit attendance
- `POST /api/attendance/manual` - Manual attendance marking
- `GET /api/attendance/records/class/:classId` - Get attendance records for class

### QR Sessions
- `POST /api/attendance/qr/generate` - Generate QR session
- `POST /api/attendance/qr/refresh` - Refresh QR token
- `POST /api/attendance/qr/terminate` - Terminate QR session

### Schedules
- `GET /api/schedules` - Get schedules
- `POST /api/schedules` - Create schedule
- `PUT /api/schedules/:id` - Update schedule
- `DELETE /api/schedules/:id` - Delete schedule

## 🛠️ Development Workflow

### Backend Development
1. All shared models and controllers are in `src/shared/`
2. Role-specific routes and controllers are in `src/student/` and `src/teacher/`
3. Use ESM syntax (import/export) as Node.js v24.4.0 is configured for ESM

### Frontend Development
1. Use Tailwind CSS for styling
2. Follow the component structure in `src/components/`
3. API calls should go through services in `src/services/`

### Mobile App Development
1. Use React Native with Expo
2. Navigation is handled by React Navigation
3. Camera and face detection features use Vision Camera and ML Kit

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For support and questions, please open an issue in the GitHub repository.