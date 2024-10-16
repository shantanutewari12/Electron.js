# Electron.js To-Do List Application

## Description:
This project is a **To-Do List Application** built using **Electron.js**, **React.js**, and **Tailwind CSS**. It runs as a desktop application using Electron, providing a simple interface to add and remove tasks. The tasks are displayed dynamically using React's state management, and the app features a clean and modern UI thanks to Tailwind CSS.

## Technologies Used:
- **Electron.js**: To create the desktop application and handle the main process.
- **React.js**: For building the interactive user interface.
- **Tailwind CSS**: For styling the components and layout with utility-first CSS.

---

## Project Structure Overview:

### 1. `main.js` (Electron Main Process):
   - The **main process** is handled by `main.js`. This script is responsible for creating and managing the main application window using Electron's `BrowserWindow`.
   - In this file:
     - A new window (`mainWindow`) is created with a width of 1000px and height of 600px.
     - The `DevTools` are opened for debugging purposes.
     - The React application (bundled by `react-scripts` inside the `build` folder) is loaded into this window using the `loadURL` method.
     - Electron listens for when the app is "ready" and then calls the `createMainWindow` function.
     - The `startUrl` is set to the `build/index.html` file, which is the entry point for the React application.

### 2. `App.tsx` (React Entry Point):
   - This file acts as the entry point for the React portion of the application.
   - It simply imports and renders the `ToDo` component, which holds the main logic for displaying and managing tasks.
   - The structure is kept minimal for cleanliness and to delegate functionality to child components (`ToDo`).

### 3. `To_Do.tsx` (React To-Do Component):
   - This is the core component where the **To-Do List** functionality is implemented.
   - **State management** is done using React's `useState` hooks:
     - `tasks`: an array that holds the list of tasks.
     - `newTask`: a string that represents the input value for the new task.
   - The user can:
     - **Add a task**: When a user types a task and clicks "Add Task," it is added to the list if it's not empty.
     - **Delete a task**: Each task has a "Delete" button, which removes it from the list when clicked.
   - The list of tasks is displayed using a `map` function, which renders each task along with its delete button inside a styled `div`.
   - The component is styled using **Tailwind CSS**, which makes it responsive and visually appealing without the need for custom CSS files.

---

## Key Concepts:

1. **Electron's Main and Renderer Process**:
   - **Main Process**: The `main.js` file runs in the main process, handling the window creation and interacting with the operating system. It loads the UI from the React app.
   - **Renderer Process**: The React app, including `app.tsx` and `to_do.tsx`, runs in the renderer process. This process handles the UI and all frontend interactions.

2. **React Components**:
   - The `ToDo` component manages the application’s state using hooks, making it easy to track and update tasks in real-time.
   - The user interface updates dynamically when tasks are added or removed.

3. **Tailwind CSS**:
   - Tailwind's utility classes (e.g., `bg-gray-900`, `text-white`, `rounded`, `p-2`) are used to build a sleek interface without writing custom CSS rules.

---

## How to Run the Application:

1. Clone the repository:
   ```bash
   git clone https://github.com/shantanutewari12/Electron.js.git
