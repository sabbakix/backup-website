---
title: "React - To-do App in React"
#summary: "How to setup OpenMediaVault as a backup server"
categories: ["React", "Web Development"]
tags: ["React", "Web Development"]
date: 2022-02-18
weight: 2
author: "Sabbadin Stefy"
draft: False
---




Let's write a simple To-Do app with React-js. We'll create components for adding, displaying, and deleting tasks.

### Project Structure:

```
your-todo-app/
├── node_modules/
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── components/
│   │   ├── TodoList.js
│   │   ├── TodoItem.js
│   │   └── TodoForm.js
│   ├── App.js
│   ├── index.js
│   └── ...
├── package.json
└── ...
```

### Steps:

1. **Create TodoItem Component:**

   ```javascript
   // src/components/TodoItem.js
   import React from 'react';

   function TodoItem({ task, onDelete }) {
     return (
       <div>
         <span>{task}</span>
         <button onClick={onDelete}>Delete</button>
       </div>
     );
   }

   export default TodoItem;
   ```

2. **Create TodoList Component:**

   ```javascript
   // src/components/TodoList.js
   import React, { useState } from 'react';
   import TodoItem from './TodoItem';

   function TodoList() {
     const [tasks, setTasks] = useState([]);

     const addTask = (task) => {
       setTasks([...tasks, task]);
     };

     const deleteTask = (index) => {
       const updatedTasks = tasks.filter((_, i) => i !== index);
       setTasks(updatedTasks);
     };

     return (
       <div>
         <h1>Todo List</h1>
         <ul>
           {tasks.map((task, index) => (
             <li key={index}>
               <TodoItem task={task} onDelete={() => deleteTask(index)} />
             </li>
           ))}
         </ul>
         <TodoForm onAdd={addTask} />
       </div>
     );
   }

   export default TodoList;
   ```

3. **Create TodoForm Component:**

   ```javascript
   // src/components/TodoForm.js
   import React, { useState } from 'react';

   function TodoForm({ onAdd }) {
     const [newTask, setNewTask] = useState('');

     const handleInputChange = (e) => {
       setNewTask(e.target.value);
     };

     const handleSubmit = (e) => {
       e.preventDefault();
       if (newTask.trim() !== '') {
         onAdd(newTask.trim());
         setNewTask('');
       }
     };

     return (
       <form onSubmit={handleSubmit}>
         <input
           type="text"
           placeholder="Add a new task"
           value={newTask}
           onChange={handleInputChange}
         />
         <button type="submit">Add Task</button>
       </form>
     );
   }

   export default TodoForm;
   ```

4. **Update App Component:**

   ```javascript
   // src/App.js
   import React from 'react';
   import TodoList from './components/TodoList';

   function App() {
     return (
       <div>
         <TodoList />
       </div>
     );
   }

   export default App;
   ```

5. **Run the App:**

   ```bash
   npm start
   ```

   Open your browser and go to [http://localhost:3000](http://localhost:3000) to see and interact with your simple To-Do app.

This example demonstrates the basic concepts of creating components, managing state, and passing data between components in a React app. You can further enhance and customize your To-Do app by adding features such as editing tasks, marking tasks as complete, or persisting tasks to a backend server.