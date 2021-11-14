# Todo List Project

This project is part of CodeSpace Project.

 This is how I solve this assignment.

## Tasks

- [x] The ‘todos’ was going to be objects that I dynamically created, using factories or constructors/classes to generate them.
  - This was made by doing two classes one for Project and another for Task as shown here:
  ```javascript 
        class Project {
            constructor(name) {
            this.projectName = name;
            this.tasks = [];
        }
    ```
  ```javascript 
        class Task {
            constructor(title, description, dueDate, priority) {
                this.taskTitle = title;
                this.taskDesc = description;
                this.taskDate = dueDate;
                this.taskPriority = priority;
                this.checked = false;
            }
        }
    ```
  - The properties which at minimum had a title, description, due date and priority. It was made by making the two classes and the object ends as an array of objects with this format to be handled by local storage:
  ```javascript
    [
        {
            projectName: string,
            tasks: [
                {
                    taskTitle: string,
                    description: string,
                    dueDate: string,
                    checked: boolean
                }
            ]
        }
    ]
  ```
- [x] the application have projects or separate lists of todos. When a user first opens the app, there is a ‘default’ project to which all of their todos are put. Users able to create new projects and choose which project their todos go into.
  - The entry point for the code is `index.js` contained in the `src` folder.
  - The render of DOM objects are made on `index.html`
- [x] I seperated  application logic (i.e. creating new todos, setting todos as complete, changing todo priority etc.) from the DOM-related stuff, so I kept all of those things in separate modules.
  - The data and constructors are located in `/src/common/` under the name of `constructor.js` and `data.js`
  - The event handlers are inside of `/src/handler` includes onclick events of add/remove Project, add/remove task, show modal, show table tabs.
  - The interface and injection of DOM are handled by files inside `/src/render` with js files to render projects / tasks or reset UI.
- The app is able to do the following:
  1. View all projects
    - All Projects are rendered by default. As you select a project it renders each task for a project. 
  3. View all todos in each project (probably just the title and duedate.. perhaps changing color for different priorities)
     - All todos tasks are rendered when clicked each project. 
  4. Expand a single todo to see/edit its details
     - Added one button for each element to show pop up task with details. 
  5. Delete a todo
    - Button delete on each task is supplied and handled by `/src/handler/removeTask.js`
    - Button delete project is global and is handled by `/src/handler/removeProject.js`
- [x] I Used localStorage to save user’s projects and todos between sessions.
  - localStorage is used in `/src/common/data.js` to save and retrieve all data needed.
  - Used [webpack](https://webpack.js.org/) with basic configuration.
  - Changed output path in order to deploy gh-pages easily. 
  ```javascript
    output: {
        filename: 'main.js',
        path: path.resolve(__dirname, 'docs'),
    }
  ```


### Technologies
- HTML
- CSS
- Vanilla JS
- Webpack
- FontAwesome




## Live preview

- Check preview on github pages -> [Link](https://javazz137.github.io/todo-list/)

