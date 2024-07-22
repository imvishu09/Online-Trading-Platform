# Online Trading Platform

This is a React Native application for an online stock trading platform.

## Features

- View stock quotes in real-time.
- Manage user favorites.
- Display detailed stock information.
- Interactive charts for stock performance.
- Light and dark theme support.
- Error handling for non-existent routes and modal screens.

## Getting Started

### Prerequisites

- Node.js and npm (or yarn) installed on your system.
- A code editor of your choice (e.g., Visual Studio Code, Atom).
- An Expo account (optional, for easier development and deployment).

### Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/imvishu09/Online-Trading-Platform.git
    ```

2. Navigate to the project directory:
    ```bash
    cd Online-Trading-Platform
    ```

3. Install dependencies:
    ```bash
    npm install
    ```

### Running the Application

#### Option 1: Using Expo (Recommended)

1. If you don't have an Expo account, sign up for free at [Expo](https://expo.dev/).

2. Start the development server:
    ```bash
    expo start
    ```

3. Follow the instructions on the screen to open the app in your Expo client or web browser.

#### Option 2: Manual Development Server

1. Start the Metro bundler:
    ```bash
    npm start
    ```

2. Open [http://localhost:19000/](http://localhost:19000/) in your web browser.

## Code Structure

- `src`: Contains the source code for the React Native application.
- `assets`: Contains static assets like images and fonts.
- `apollo`: Contains configuration for Apollo Client and GraphQL integration.
- `components`: Reusable UI components.
- `screens`: Screens for different functionalities (e.g., home screen, stock details screen).
- `navigation`: Navigation configuration using Expo Router.
- `styles`: Global styles and theme definitions.
- `utils`: Utility functions used throughout the application.

## Example Code

### NotFoundScreen Component

This component renders a screen displayed when the user tries to access a non-existent route.

```javascript
import { Link, Stack } from 'expo-router';
import { StyleSheet } from 'react-native';
import { Text, View } from '@/src/components/Themed';

export default function NotFoundScreen() {
  return (
    <>
      <Stack.Screen options={{ title: 'Oops!' }} />
      <View style={styles.container}>
        <Text style={styles.title}>This screen doesn't exist.</Text>
        <Link href="/" style={styles.link}>
          <Text style={styles.linkText}>Go to home screen!</Text>
        </Link>
      </View>
    </>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    padding: 20,
  },
  title: {
    fontSize: 20,
    fontWeight: 'bold',
  },
  link: {
    marginTop: 15,
    paddingVertical: 15,
  },
  linkText: {
    fontSize: 14,
    color: '#2e78b7',
  },
});
```

### ModalScreen Component

This component renders the content of a modal screen.

```javascript
import { StatusBar } from 'expo-status-bar';
import { Platform, StyleSheet } from 'react-native';
import { Text, View } from '@/src/components/Themed';

export default function ModalScreen() {
  return (
    <View style={styles.container}>
      <StatusBar style={Platform.OS === 'ios' ? 'light' : 'auto'} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
});
```

