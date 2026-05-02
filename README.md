
# Getting Started with React.js Through AI-Assisted Learning

## Building a Functional Todo Application

---

## 1. Title & Objective

### **Title**

Getting Started with React.js – Building a Todo App Using AI-Assisted Learning

### **Technology Chosen**

React.js (with Vite)

### **Why I Chose This Technology**

As a frontend development student with prior knowledge of HTML, CSS, and vanilla JavaScript, I selected React.js because it represents the modern standard for building dynamic and scalable user interfaces. Unlike traditional DOM manipulation in vanilla JavaScript, React introduces a declarative and component-based approach, which simplifies UI development and improves maintainability.

Additionally, React is highly used in the software industry, making it a valuable skill for career development.

### **End Goal**

The objective of this project was to:

* Learn React fundamentals using AI assistance
* Build a simple but functional Todo application
* Understand state management and dynamic rendering
* Document the entire learning process for reproducibility

---

## 2. Quick Summary of the Technology

### **What is React?**

React is a JavaScript library developed by Meta (Facebook) for building user interfaces. It allows developers to create reusable UI components and manage application state efficiently using a virtual DOM.

### **Key Characteristics**

* Component-based architecture
* Declarative UI design
* Efficient updates using the virtual DOM
* Strong ecosystem and community support

### **Where React is Used**

* Single Page Applications (SPAs)
* Dashboards and admin panels
* E-commerce platforms
* Social media applications

### **Real-World Example**

Applications like Instagram and Facebook use React to dynamically update user interfaces without reloading the entire page.

---

## 3. System Requirements

To successfully run this project, the following tools and environment were required:

* **Operating System:** Windows / Linux / macOS
* **Node.js:** Version 16 or higher
* **npm:** Installed with Node.js
* **Code Editor:** Visual Studio Code
* **Web Browser:** Google Chrome (or any modern browser)

---

## 4. Installation & Setup Instructions

The project was initialized using Vite, a modern build tool that provides fast development performance.

### Step 1: Create the Project

```bash
npm create vite@latest react-todo-app
```

### Step 2: Navigate into the Project Directory

```bash
cd react-todo-app
```

### Step 3: Install Dependencies

```bash
npm install
```

### Step 4: Start Development Server

```bash
npm run dev
```

### Step 5: Open in Browser

Navigate to:

```
http://localhost:5173
```

---

## 5. Minimal Working Example (Todo Application)

### **Overview of the Application**

The application is a simple Todo list that allows users to:

* Add tasks
* Mark tasks as completed
* Delete tasks

It demonstrates fundamental React concepts including state management, event handling, and dynamic UI updates.
Project Structure
react-todo-app/
│
├── public/
├── src/
│   ├── App.jsx
│   ├── main.jsx
│   ├── index.css
│
├── package.json
├── vite.config.js
├── README.md

---

### **Core Implementation Code**

```jsx
import { useState } from "react";

function App() {
  const [input, setInput] = useState("");
  const [todos, setTodos] = useState([]);

  const addTodo = () => {
    if (input.trim() === "") return;

    const newTodo = {
      id: Date.now(),
      text: input,
      completed: false,
    };

    setTodos([...todos, newTodo]);
    setInput("");
  };

  const toggleTodo = (id) => {
    setTodos(
      todos.map((todo) =>
        todo.id === id
          ? { ...todo, completed: !todo.completed }
          : todo
      )
    );
  };

  const deleteTodo = (id) => {
    setTodos(todos.filter((todo) => todo.id !== id));
  };

  return (
    <div>
      <h1>Todo App</h1>

      <input
        value={input}
        onChange={(e) => setInput(e.target.value)}
        placeholder="Enter task"
      />

      <button onClick={addTodo}>Add</button>

      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>
            <span
              onClick={() => toggleTodo(todo.id)}
              style={{
                textDecoration: todo.completed ? "line-through" : "none",
                cursor: "pointer",
              }}
            >
              {todo.text}
            </span>

            <button onClick={() => deleteTodo(todo.id)}>
              Delete
            </button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

---

### **Expected Output**

* A heading labeled “Todo App”
* An input field for entering tasks
* A button to add tasks
* A dynamically updated list of todos
* Ability to toggle completion (strikethrough effect)
* Ability to delete tasks

---

## 6. AI Prompt Journal

AI was used as a guided learning assistant throughout this project.

### **Prompt 1**
Create a learning plan: I am a frontend developer student with knowledge of html and css vanila js and want to react Could you help me create a structured learning journey plan with: - 3-4 distinct learning phases - Prerequisites for each phase - 4-5 specific learning steps per phase - Verification activities for each phase
response


### **Prompt 2*
High-Level Conceptual Introduction
I'd like you to be my react tutor as I learn it coming from vanilla js html and css. Instead of giving direct answers, please: - Ask me guiding questions - Break down complex concepts into smaller pieces - Give hints when I'm stuck - Point out conceptual differences from html css and js - Correct misunderstandings gently Let's start with phase 1 from my learning plan up to phase four.
**“Provide step-by-step guidance to build a React Todo App.”**

* Enabled structured learning
* Broke down development into manageable steps
* Encouraged active problem-solving

---

### **Prompt 3**
 Guided Installation and First Application
 "You are an expert react tutor. I am a developer proficient in html  css and vanilla js and have completed a conceptual overview of react. Now, I want a single, continuous, hands-on lesson to get from zero to a running command-line application. 

Please guide me one step at a time, asking for confirmation before moving to the next step.

The lesson should cover:

Installation: The correct, idiomatic way to install react and node js on Windows. Explain why each step is necessary and what common mistakes to avoid (like using Linux commands on Windows). 
Verification: How to verify the installation was successful.
Project Creation: Using react to create a to do list. 
Coding: Writing the code for a simple interactive to do list. Explain the code as you go. 
For every part of this lesson, show the exact commands and code snippets with inline comments."
prompt 4

**“Help debug syntax errors in a React component.”**
I need help diagnosing the root cause of an error in my [react js ] application.

Here's the error and stack trace:

[[plugin:vite:oxc] Transform failed with 1 error:

[PARSE_ERROR] Error: Expected `}` but found `EOF`
    ╭─[ src/App.jsx:34:20 ]
    │
  3 │ function App() {
    │                ┬  
    │                ╰── Opened here
    │ 
 34 │ export default App;
    │                    │ 
    │                    ╰─ `}` expected
────╯
C:/Users/ADMIN/Desktop/my-first-react-app/src/App.jsx
    at transformWithOxc (file:///C:/Users/ADMIN/Desktop/my-first-react-app/node_modules/vite/dist/node/chunks/node.js:3343:19)
    at TransformPluginContext.transform (file:///C:/Users/ADMIN/Desktop/my-first-react-app/node_modules/vite/dist/node/chunks/node.js:3411:26)
    at EnvironmentPluginContainer.transform (file:///C:/Users/ADMIN/Desktop/my-first-react-app/node_modules/vite/dist/node/chunks/node.js:30164:51)
    at async loadAndTransform (file:///C:/Users/ADMIN/Desktop/my-first-react-app/node_modules/vite/dist/node/chunks/node.js:24512:26)
    at async viteTransformMiddleware (file:///C:/Users/ADMIN/Desktop/my-first-react-app/node_modules/vite/dist/node/chunks/node.js:24306:20)
Click outside, press Esc key, or fix the code to dismiss.
You can also disable this overlay by setting server.hmr.overlay to false in vite.config.js.
* Assisted in identifying missing braces and JSX errors
* Improved debugging skills

---

### **Evaluation of AI Usage**

AI proved highly effective in:

* Explaining complex concepts simply
* Providing real-time debugging support
* Structuring the learning process

However, critical thinking was still required to understand and apply the concepts correctly.

---

## 7. Common Issues & Solutions

### **1. Syntax Errors (Missing Braces or Tags)**

* **Issue:** Application failed to compile
* **Solution:** Carefully matched opening and closing brackets and JSX tags

---

### **2. State Not Updating**

* **Issue:** UI not reflecting changes
* **Solution:** Ensured correct use of `useState` and immutability principles

---

### **3. Event Handlers Not Working**

* **Issue:** Button clicks not triggering actions
* **Solution:** Used correct syntax for event handlers (e.g., `onClick={() => function()}`)

---

### **4. List Rendering Errors**

* **Issue:** React warnings about keys
* **Solution:** Assigned unique IDs to each todo using `Date.now()`

---

## 8. References

* React Official Documentation: [https://react.dev](https://react.dev)
* Vite Documentation: [https://vitejs.dev](https://vitejs.dev)
* MDN Web Docs (JavaScript): [https://developer.mozilla.org](https://developer.mozilla.org)
* JSONPlaceholder API: [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com)

---

## 9. Key Learnings & Reflection

Through this project, I gained:

* A clear understanding of React’s component-based architecture
* Practical experience with `useState` for managing dynamic data
* Insight into how React differs from traditional DOM manipulation
* Experience using AI as a learning and debugging tool
* Confidence in building a functional frontend application

### **Reflection**

The use of AI significantly accelerated the learning process by providing guidance and explanations on demand. However, actively engaging with the material and debugging errors independently was essential for deeper understanding.

---

## 10. Conclusion

This project successfully demonstrated how AI can be used as a powerful tool for learning new technologies. By building a Todo application, I was able to apply React fundamentals in a practical context and develop a reusable workflow for learning future technologies.

The final outcome is a functional React application and a documented learning process that can be replicated by other beginners.

---
