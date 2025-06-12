# CaféFinder ☕️

A React Native (Expo) app to find nearby coffee shops and view details, using a local mock server.

---

## Technologies Used

- **Expo** (React Native framework)
- **React Native Maps** for the interactive map
- **React Native Safe Area Context** for safe area handling on iOS and Android
- **@tanstack/react-query** for data fetching and caching
- **expo-location** for requesting user location
- **react-error-boundary** for global error handling
- **react-navigation** and **expo-router** for navigation
- **Local Node.js/Express server** to simulate the coffee shop API  
  (at `src/scripts/cafes-mock-server/server.js`)
- Others: TypeScript, Zustand, ESLint, etc.

---

## Installation & Run Instructions

1. **Clone the repository**  
   ```bash
   git clone [YOUR_REPO_URL]
   cd [repo-name]
   ```

2. **Install dependencies**
   ```bash
   yarn install
   ```

3. **Start the local mock server**  
   > ⚠️ _You must do this **before** running the app_

   ```bash
   cd src/scripts/cafes-mock-server
   yarn install
   node server.js
   ```

   The server will start at `http://localhost:3001/` (or the port shown in the terminal).

4. **Start the app in development mode (Expo)**
   - Go back to the project root:
     ```bash
     cd ../../../..
     ```
   - Start Expo:
     ```bash
     npx expo start
     ```

5. **Open the app on a simulator or physical device**
   - **iOS:** Press `i` in the Expo terminal to launch on iOS Simulator, or scan the QR code with the Expo Go app.
   - **Android:** Press `a` for Android Emulator, or scan the QR with Expo Go.
   - > Make sure to accept all location permissions on your device.

---

## Design and Architecture Decisions

- **Feature-based structure:** Components, hooks, and constants are organized by feature/screen for scalability.
- **External mock server:** The local server enables fast iteration without a real backend; data is randomly generated on each launch.
- **Centralized permissions modal:** Users are prompted to grant required permissions before using the app.
- **Cross-platform UI:** `SafeAreaView` and responsive styles ensure good UX on both iOS and Android.
- **Global ErrorBoundary:** Catches any unexpected JavaScript errors, displaying a friendly error screen instead of crashing.
- **Reusable custom hooks:** Permission, map, filter, and modal logic is encapsulated in custom hooks for clarity and reusability.
- **React Query:** Used for efficient data caching and refetching.
- **Zustand store for state:** The selected coffee shop is stored in a global store, making context available throughout navigation.

---

## Additional Notes

- **Important:** The app will only work correctly if the mock server is running.
- **TypeScript codebase:** The entire project is written in TypeScript.

---

