# ReactGuard: Mastering Error Handling

## Overview
ReactGuard is a Next.js project that demonstrates how to gracefully handle JavaScript errors using React Error Boundaries.  

The project walks through creating an ErrorBoundary class component, integrating it into the application, testing it with an error-prone component, and extending functionality by logging errors with Sentry.

## Learning Objectives
- Understand how **React Error Boundaries** work  
- Implement a **class component** in TypeScript  
- Handle runtime errors gracefully in a **Next.js application**  
- Integrate third-party **error monitoring services** (e.g., Sentry)  
- Test error handling components effectively  

## Key Concepts
- **Error Boundaries** – Special React components that catch JavaScript errors anywhere in their child component tree  
- **Lifecycle Methods** – Using getDerivedStateFromError and componentDidCatch to handle errors  
- **Error Monitoring** – Integrating services like **Sentry** for production error tracking  
- **Fallback UI** – Displaying user-friendly error messages when something goes wrong  
- **Error Recovery** – Allowing users to retry rendering with a **“Try again”** button  

## 🛠 Tools and Libraries
- **React** – JavaScript library for building UIs  
- **TypeScript** – Superset of JavaScript with static typing  
- **Next.js** – React framework for server-rendered applications  
- **Sentry** – Error monitoring and tracking service  
- **Node.js / npm** – Runtime environment and package manager  

## 📂 Project Tasks

### **Task 0: Implement ErrorBoundary**
- **Objective**: Create a reusable ErrorBoundary class component in TypeScript.  
- **Details**:
  - Extends React.Component with ErrorBoundaryProps and State.  
  - Implements getDerivedStateFromError to update state when an error occurs.  
  - Implements componentDidCatch to log error details.  
  - Provides a **fallback UI** with a recovery button.  

### **Task 1: Integrate ErrorBoundary**
- **Objective**: Wrap the entire Next.js app with the ErrorBoundary.  
- **Details**:
  - Updated _app.tsx to wrap `<Component {...pageProps} />` inside `<ErrorBoundary>`.  
  - Ensures **all pages and components** are protected from crashes.  

### **Task 2: Test with ErrorProneComponent**
- **Objective**: Create a component that **intentionally throws an error** to test the boundary.  
- **Details**:
  - ErrorProneComponent immediately throws an error when rendered.  
  - Imported into pages/index.tsx and wrapped in <ErrorBoundary>.  
  - Verifies fallback UI is displayed instead of a crash.  

### **Task 3: Add Error Monitoring**
- **Objective**: Integrate Sentry to track and log errors.  
- **Details**:
  - Installed Sentry SDK:  
    ```bash
    npm install @sentry/react @sentry/nextjs
    ```
  - Configured Sentry with dsn from dashboard.  
  - Modified componentDidCatch to call Sentry.captureException(error, { extra: errorInfo }).  
  - Verified that errors from ErrorProneComponent show up in **Sentry Dashboard**.  

## 🌍 Real-World Use Case
Error boundaries are critical in production apps to:  
1. Prevent app-wide crashes caused by a single component.  
2. Provide **meaningful error messages** instead of blank screens.  
3. Track and monitor errors in real-time.  
4. Let users **recover from non-critical issues** without reloading the app.  
5. Maintain **application stability and user trust**.  

This implementation pattern is widely used by **enterprise-level web apps**.  

## ⚙️ Implementation Summary
- ✅ Built an **ErrorBoundary** class component with TypeScript interfaces.  
- ✅ Wrapped the application in _app.tsx to globally handle errors.  
- ✅ Developed an ErrorProneComponent to simulate crashes.  
- ✅ Integrated **Sentry** for error tracking and monitoring.  
- ✅ Implemented **fallback UI** with recovery support.  

This demonstrates **React best practices** for robust error handling in modern web development.  

## 🚀 Getting Started
1. Clone the repository  
   ```bash
   git clone https://github.com/your-username/reactguard-error-handling.git
   cd reactguard-error-handling