## MicroboxLabs Fullstack Challenge

### Task Management System
This project is a technical test that contains the design and implementation of a task management system using Next.js, Tailwind CSS and Flowbite. The system will help MicroboxLabs assign and manage tasks efficiently, with capabilities to assign tasks to users or groups.

## Requirements
 - NodeJs installed

## Construction 🛠️
* **Language:** JavaScript
* **Framework:** Next.js
* **UI library:** Tailwind CSS and Flowbite
* **Database:** SQLite

## Installation
1) Clone repository.
2) Run ```npm install ```.
3) Run ```node nextjs-task-system/app/db/initDB.js```

## Execution
Open your favorite Terminal and run this commands.

    npm run dev 

## API
### Login 
    POST /login
    body: { email : string, 
            pass: string }  
### Users
#### Get users
    GET  /users
#### Create user
    POST  /users
    body: { username : string,
            email : string, 
            pass: string, 
            rol : enum('admin','regular') }
### Groups
#### Get groups
    GET  /groups
#### Create group
    POST  /groups
    body: { name : string }
#### Get group by user
    GET  /groups/user?user_id=${user_id}
#### Add user in a group
    POST  /groups/user
    body: { group_id: int,
            user_id: int }
### Tasks
#### Get tasks
    GET  /tasks
#### Create user
    POST  /tasks
    body: { title : string,
            description : string, 
            assigned_to: string, 
            assigned_to_id: int, 
            assigned_to_id: enum('user','group'), 
            due_date: date,
            priority: enum('low','medium', 'high')}
#### Update user
    PUT  /tasks
    body: { id: int,
            title : string,
            description : string, 
            assigned_to: string, 
            assigned_to_id: int, 
            assigned_to_id: enum('user','group'), 
            due_date: date,
            status: enum('pending','in progress', 'completed')
            priority: enum('low','medium', 'high')}
#### Delete task
    DELETE  /tasks?id=${id}
#### Get tasks by user
    GET  /tasks/user?user_id=${user_id}
#### Get comments by task
    GET  /tasks/comments?task_id=${task_id}
#### Add comment in a task
    POST  /tasks/comments
    body: { task_id: int,
            user_id: int,
            comment: string}
            
## Testing 
To login use the registered users:

#### Users:

| Username | Email | Password | Rol | 
| ----------- | ----------- | ----------- | ----------- |
| admin | admin@gmail.com | admin123 | admin |
| front | front@gmail.com | front123 | regular |
| back | back@gmail.com | back123 | regular |
| QA | QA@gmail.com | qa123 | regular |

#### Groups:

| Name | Users |
| ----------- | ----------- |
| Development Team | front - back |
| FrontEnd Team | front |
| BackEnd Team | back | 
| QA Team | QA |


### Documentation
* **Next.js:** https://nextjs.org/
* **Tailwind:** https://tailwindcss.com/
* **Flowbite** https://flowbite-react.com/
* **SQLite:** https://www.sqlite.org/



