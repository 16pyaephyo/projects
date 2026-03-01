# To-Do List Project Case Study

## Project: Interactive To-Do List

### Description
A **dynamic To-Do List application** built with HTML, CSS, and JavaScript.  
Users can **add, delete, and clear tasks**, with **real-time updates**, keyboard support, and persistent storage using **localStorage**.

---

## Problem-Solving Process
- Define project goal: Create a functional to-do list that persists tasks across sessions.
- Plan UI: Card layout with input field, add button, task list, task count, and clear-all button.
- Implement logic:
  - Use `tasks` array to hold objects with `id` and `text`
  - Render tasks dynamically into the DOM
  - Handle click events for adding, deleting, and clearing tasks
  - Update task count automatically
- Handle edge cases:
  - Ignore empty input
  - Properly delete tasks using unique `id`
  - Update task count correctly
- Enhance UX:
  - Press Enter to add task
  - Smooth styling and hover effects
  - Responsive card layout

---

## UI/UX Decisions
- **Card layout**: Focuses attention and centralizes task interaction
- **Task count**: Keeps user informed about progress
- **Buttons**: Clear hover/click effects for interactivity
- **Input feedback**: Ignore empty inputs to prevent errors
- **Responsive design**: Works well on mobile and desktop

---

## JavaScript Struggles & Solutions

| Problem | Solution |
|---------|---------|
| Tasks not rendering correctly | Created `renderTasks()` to rebuild DOM every change |
| Deleting wrong task | Assigned unique `id` to each task, used `data-id` attribute |
| Task count not updating | Updated count inside `renderTasks()` after each render |
| Handling Enter key | Added `keydown` listener on input to call `addTask()` |
| Persisting tasks | Used `localStorage` to save and load tasks |
| Keeping nextId consistent | Saved `nextId` in localStorage and recalculated on load |

---

## Before & After Example (small snippets)

**Before (tasks array without unique ID, delete confused)**

```js
tasks.push(taskInput.value);
```
```js
**After (unique ID and structured object)**

tasks.push({ id: nextId++, text: taskInput.value.trim() });
```
**Before (delete button had no effect)**
```js
del.addEventListener('click', () => {
    tasksContainer.removeChild(item);
});
```
**After (delete correct task by id)**
```js
del.addEventListener('click', () => {
    deleteTask(task.id);
});
```
**Before (tasks disappear on refresh)**
```js
// No storage logic
```
**After (persist tasks with localStorage)**
```js
function saveTasks(){
    localStorage.setItem('todo-tasks', JSON.stringify(tasks));
    localStorage.setItem('todo-nextId', String(nextId));
}

(function loadSaved(){
    const saved = localStorage.getItem('todo-tasks');
    const savedId = localStorage.getItem('todo-nextId');
    if(saved){
        tasks = JSON.parse(saved);
        nextId = savedId ? Number(savedId) : (tasks.length ? Math.max(...tasks.map(t=>t.id))+1 : 1);
        renderTasks();
    }
})();
```

## Key Learning Points

- Dynamic DOM manipulation with createElement, appendChild, and dataset
- Handling multiple event types (click, keydown)
- State management for task list with unique IDs
- Updating UI reactively (task list and count)
- Persisting data across sessions with localStorage
- Implementing beginner-friendly error handling (ignore empty input)
- Structuring code for readability and maintainability