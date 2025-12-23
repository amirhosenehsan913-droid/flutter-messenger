# Flutter Messenger App

A modern, feature-rich messaging application built with Flutter that enables real-time communication between users.

## 📋 Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Usage](#usage)
- [Architecture](#architecture)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## ✨ Features

- **Real-time Messaging**: Send and receive messages instantly
- **User Authentication**: Secure user registration and login
- **Contact Management**: Manage your contacts and friends list
- **Message History**: View complete message history with conversations
- **User Profiles**: View and customize user profiles
- **Online Status**: See who's online and available
- **Message Notifications**: Push notifications for incoming messages
- **Media Sharing**: Share images and files with other users
- **Group Chats**: Create and manage group conversations
- **Search Functionality**: Search through conversations and contacts
- **Dark Mode Support**: Beautiful dark theme support
- **Offline Support**: Store messages locally with sync when online

## 🔧 Prerequisites

Before you begin, ensure you have the following installed:

- **Flutter**: Version 3.0 or higher ([Install Flutter](https://flutter.dev/docs/get-started/install))
- **Dart**: Version 2.17 or higher (comes with Flutter)
- **Android Studio** or **Xcode** (for iOS development)
- **Git**: For version control
- **Firebase Account**: For backend services (optional, depending on your configuration)

### Minimum Requirements

- **Android**: Minimum SDK version 21 (Android 5.0)
- **iOS**: Minimum deployment target iOS 11.0

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/amirhosenehsan913-droid/flutter-messenger.git
cd flutter-messenger
```

### 2. Install Dependencies

```bash
flutter pub get
```

### 3. Generate Build Files (if needed)

```bash
flutter pub run build_runner build
```

### 4. Run the Application

#### On Android:
```bash
flutter run -d android
```

#### On iOS:
```bash
flutter run -d ios
```

#### On Web:
```bash
flutter run -d web
```

## 📁 Project Structure

```
flutter-messenger/
├── lib/
│   ├── main.dart                 # App entry point
│   ├── models/                   # Data models
│   │   ├── user_model.dart
│   │   ├── message_model.dart
│   │   ├── conversation_model.dart
│   │   └── chat_room_model.dart
│   ├── screens/                  # UI Screens
│   │   ├── auth/
│   │   │   ├── login_screen.dart
│   │   │   ├── signup_screen.dart
│   │   │   └── forgot_password_screen.dart
│   │   ├── home/
│   │   │   ├── home_screen.dart
│   │   │   ├── conversations_screen.dart
│   │   │   └── contacts_screen.dart
│   │   ├── chat/
│   │   │   ├── chat_screen.dart
│   │   │   └── chat_details_screen.dart
│   │   ├── profile/
│   │   │   ├── profile_screen.dart
│   │   │   └── edit_profile_screen.dart
│   │   └── common/
│   │       ├── splash_screen.dart
│   │       └── settings_screen.dart
│   ├── services/                 # Business logic & APIs
│   │   ├── auth_service.dart
│   │   ├── message_service.dart
│   │   ├── user_service.dart
│   │   └── notification_service.dart
│   ├── widgets/                  # Reusable widgets
│   │   ├── message_bubble.dart
│   │   ├── user_tile.dart
│   │   ├── custom_button.dart
│   │   └── custom_text_field.dart
│   ├── providers/                # State management (Provider/Riverpod)
│   │   ├── auth_provider.dart
│   │   ├── message_provider.dart
│   │   ├── user_provider.dart
│   │   └── theme_provider.dart
│   ├── utils/                    # Utilities
│   │   ├── constants.dart
│   │   ├── validators.dart
│   │   ├── extensions.dart
│   │   └── helpers.dart
│   └── config/                   # Configuration files
│       ├── routes.dart
│       └── theme.dart
├── assets/
│   ├── images/                   # App images
│   ├── icons/                    # App icons
│   └── fonts/                    # Custom fonts
├── pubspec.yaml                  # Flutter dependencies
├── pubspec.lock                  # Lock file
├── analysis_options.yaml         # Dart analysis options
├── README.md                     # This file
└── LICENSE                       # License file
```

## ⚙️ Configuration

### 1. Firebase Configuration (if applicable)

If your app uses Firebase, follow these steps:

#### Android:
1. Download `google-services.json` from Firebase Console
2. Place it in `android/app/`
3. Ensure Firebase plugins are configured in `android/build.gradle`

#### iOS:
1. Download `GoogleService-Info.plist` from Firebase Console
2. Add it to your Xcode project
3. Ensure CocoaPods dependencies are installed

### 2. Environment Variables

Create a `.env` file in the project root (if using environment package):

```
API_BASE_URL=https://your-api-url.com
FIREBASE_PROJECT_ID=your-firebase-project-id
```

### 3. Update Configuration Files

Edit `lib/config/constants.dart` with your app-specific settings:

```dart
class AppConstants {
  static const String appName = 'Flutter Messenger';
  static const String apiBaseUrl = 'https://api.example.com';
  // ... other constants
}
```

## 🚀 Usage

### Running in Development Mode

```bash
flutter run
```

### Running in Release Mode

```bash
flutter run --release
```

### Building APK (Android)

```bash
flutter build apk --release
```

### Building iOS App

```bash
flutter build ios --release
```

### Running Tests

```bash
# Run all tests
flutter test

# Run tests with coverage
flutter test --coverage
```

## 🏗️ Architecture

This project follows the **Clean Architecture** pattern with **Provider/Riverpod** for state management:

### Layers:

1. **Presentation Layer** (`screens/`, `widgets/`, `providers/`)
   - UI Components
   - State Management
   - User interactions

2. **Domain Layer** (`models/`)
   - Data models
   - Business logic entities

3. **Data Layer** (`services/`)
   - API calls
   - Local storage
   - Repository patterns

4. **Utilities & Config** (`utils/`, `config/`)
   - Helper functions
   - App configuration
   - Constants

### State Management

The app uses **Provider** / **Riverpod** for state management. Key providers:

- `AuthProvider`: Authentication state
- `MessageProvider`: Messages state
- `UserProvider`: User data state
- `ThemeProvider`: Theme configuration

## 📝 Dependencies

Key dependencies used in this project:

```yaml
- flutter: Core framework
- provider: State management
- dio: HTTP client
- firebase_core: Firebase initialization
- firebase_auth: Authentication
- firebase_database: Real-time database
- firebase_storage: File storage
- firebase_messaging: Push notifications
- local_auth: Biometric authentication
- shared_preferences: Local storage
- intl: Internationalization
- image_picker: Image selection
- permission_handler: Platform permissions
- cached_network_image: Image caching
```

See `pubspec.yaml` for complete list.

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Standards

- Follow Dart style guide ([Effective Dart](https://dart.dev/guides/language/effective-dart))
- Use meaningful variable and function names
- Write comments for complex logic
- Maintain test coverage above 80%

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 💬 Support

For support and questions:

- **Issues**: Open an issue on [GitHub Issues](https://github.com/amirhosenehsan913-droid/flutter-messenger/issues)
- **Email**: Contact the development team
- **Documentation**: Check the [Wiki](https://github.com/amirhosenehsan913-droid/flutter-messenger/wiki) for detailed guides

## 🙏 Acknowledgments

- Flutter team for the amazing framework
- Firebase for backend services
- All contributors who have helped with this project

---

**Last Updated**: December 23, 2025

**Developed with ❤️ by [amirhosenehsan913-droid](https://github.com/amirhosenehsan913-droid)**