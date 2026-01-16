# OTP Verification - Creative Dock Bootcamp Assignment

A React Native OTP (One-Time Password) verification screen built as part of the Creative Dock hiring bootcamp. This project demonstrates clean architecture, reusable components, and attention to UI/UX details.

---

## 📱 Screenshots

### iOS

| Light Mode | Dark Mode |
|:----------:|:---------:|
| ![iOS Light](./screenshots/ios-light.png) | ![iOS Dark](./screenshots/ios-dark.png) |

### Android

| Light Mode | Dark Mode |
|:----------:|:---------:|
| ![Android Light](./screenshots/Android-light.png) | ![Android Dark](./screenshots/Android-dark.png) |

---

## ✨ Features

### Core Features (Assignment Requirements)
- ✅ **4-Digit OTP Input** - Clean, accessible OTP input with auto-focus navigation
- ✅ **Verify Button** - Logs OTP to console with mocked network delay
- ✅ **Resend Timer** - 60-second countdown with disabled state
- ✅ **Timer Display** - Visual countdown shown while resend is disabled

### Additional Features
- 🌓 **Dark/Light Theme Support** - Automatic OS theme detection with seamless switching
- 📱 **Portrait & Landscape Orientation** - Responsive layouts for both orientations
- ⌨️ **Keyboard Handling** - Smart keyboard avoidance and numeric keyboard
- 📋 **Auto-fill Support** - SMS OTP auto-fill on both iOS and Android
- 🔄 **Loading State** - Visual feedback during OTP verification
- ♿ **Accessibility** - Proper accessibility labels and roles
- 🎨 **Reusable Components** - Modular component architecture

---

## 🛠 Tech Stack

| Technology | Purpose |
|------------|---------|
| React Native | Mobile framework |
| TypeScript | Type safety |
| React Navigation | Navigation |
| react-native-keyboard-controller | Keyboard handling |

---

## 📁 Project Structure

```
src/
├── components/
│   ├── CommonBox/          # Screen wrapper with StatusBar handling
│   ├── CommonButton/       # Reusable button component
│   ├── CommonOtpInput/     # Reusable OTP input component
│   ├── CommonText/         # Typography component
│   ├── CommonLoader/       # Loading indicator
│   └── index.ts
├── screens/
│   └── OtpScreen/          # OTP verification screen
├── themes/
│   ├── context/            # Theme context provider
│   ├── list/
│   │   ├── lightTheme.ts   # Light theme colors
│   │   └── darkTheme.ts    # Dark theme colors
│   └── index.ts
├── utils/
│   ├── Pixelate.ts         # Responsive sizing utilities
│   ├── useOrientation.ts   # Orientation detection hook
│   └── index.ts
└── navigation/
    └── InitialRoute.tsx    # App entry point
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js >= 18
- React Native development environment ([Setup Guide](https://reactnative.dev/docs/set-up-your-environment))
- Xcode (for iOS)
- Android Studio (for Android)

### Installation

1. **Clone the repository**
   ```sh
   git clone https://gitlab.com/creativedock1/bootcamp-otp.git
   cd bootcamp-otp
   ```

2. **Install dependencies**
   ```sh
   # Using npm
   npm install

   # OR using Yarn
   yarn install
   ```

3. **Install iOS dependencies**
   ```sh
   bundle install
   bundle exec pod install
   ```

### Running the App

1. **Start Metro bundler**
   ```sh
   npm start
   # OR
   yarn start
   ```

2. **Run on Android**
   ```sh
   npm run android
   # OR
   yarn android
   ```

3. **Run on iOS**
   ```sh
   npm run ios
   # OR
   yarn ios
   ```

---

## 🎯 Assignment Acceptance Criteria

| Requirement | Status |
|-------------|--------|
| OTP should be 4 digits long | ✅ Completed |
| Verify button logs 4-digit OTP to console | ✅ Completed |
| Mock network delay on verification | ✅ Completed |
| Resend button disabled for 60 seconds | ✅ Completed |
| Timer visible during countdown | ✅ Completed |
| Additional features for the use case | ✅ Theme support, orientation handling, accessibility |

---

## 📖 Component Usage

### CommonOtpInput

```tsx
<CommonOtpInput
  otpLength={4}
  otp={otpState}
  updateOtpValue={(val) => setOtpState(val)}
  onValidationChange={(isValid) => setIsValid(isValid)}
/>
```

### Theme Hook

```tsx
const { theme, isDark, setThemeMode } = useTheme();

// Access colors
const backgroundColor = theme.colors.background;

// Check dark mode
if (isDark) {
  // Dark mode specific logic
}

// Change theme
setThemeMode('light' | 'dark' | 'system');
```

### Orientation Hook

```tsx
const { isPortrait, isLandscape, screenWidth, screenHeight } = useOrientation();

// Responsive styling
<View style={isPortrait ? styles.portrait : styles.landscape}>
```

---

## 🧪 Testing

This project uses **Jest** and **React Native Testing Library** for unit and integration testing.

### Running Tests

```sh
# Run all tests
npm test
# OR
yarn test

# Run tests in watch mode
npm test -- --watch
# OR
yarn test --watch

# Run tests with coverage
npm test -- --coverage
# OR
yarn test --coverage

# Run specific test file
npm test -- CommonOtpInput.test.tsx
```

### Test Structure

```
__tests__/
├── components/
│   ├── CommonOtpInput.test.tsx
│   └── CommonBox.test.tsx
├── screens/
│   └── OtpScreen.test.tsx
├── hooks/
│   └── useOrientation.test.ts
├── themes/
│   └── ThemeContext.test.tsx
└── utils/
    └── testUtils.tsx
```

### Test Coverage

| Component | Coverage |
|-----------|----------|
| CommonOtpInput | Input handling, validation, accessibility |
| OtpScreen | Rendering, timer, verification flow |
| useOrientation | Portrait/landscape detection |
| ThemeContext | Theme switching, system detection |
| CommonBox | StatusBar, loader, scroll handling |

### Key Test Cases

- ✅ OTP input accepts only numeric values
- ✅ Auto-focus moves to next input on digit entry
- ✅ Backspace moves focus to previous input
- ✅ Paste handling for full OTP
- ✅ Resend timer countdown (60 seconds)
- ✅ Timer format displays correctly (00:09)
- ✅ Theme switching (light/dark/system)
- ✅ Orientation changes (portrait/landscape)
- ✅ Accessibility attributes present

---

## 🔧 Troubleshooting

If you encounter issues:

1. **Clear Metro cache**
   ```sh
   npm start -- --reset-cache
   ```

2. **Clean and rebuild**
   ```sh
   # Android
   cd android && ./gradlew clean && cd ..

   # iOS
   cd ios && rm -rf build Pods Podfile.lock && pod install && cd ..
   ```

3. **Check React Native docs**
   - [Troubleshooting Guide](https://reactnative.dev/docs/troubleshooting)

---

## 📄 License

This project is created as part of the Creative Dock hiring bootcamp assignment.

---

## 👤 Author

Built with ❤️ for Creative Dock
