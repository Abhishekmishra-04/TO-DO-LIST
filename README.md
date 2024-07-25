# TO-DO-LIST
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #289968;
        }

        .container {
            text-align: center;
            background-color: #c5c795;
            height: 600px;
            width: 800px;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        input {
            padding: 8px;
            font-size: 20px;
            width: 300px;
        }

        button {
            padding: 8px;
            cursor: pointer;
            margin-left: 10px;
            font-size: 20px;
        }

        .completed {
            text-decoration: line-through;
            color: #888;
        }

        ul {
            list-style: none;
            padding: 0;
        }

        li {
            margin: 10px 0;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>To-Do List</h1>
    <div>
        <input type="text" id="taskInput" placeholder="Add a new task">
        <button onclick="addTask()">Add</button>
    </div>
    <ul id="taskList"></ul>
</div>

<script>
    function addTask() {
        const taskInput = document.getElementById('taskInput');
        const taskList = document.getElementById('taskList');

        if (taskInput.value.trim() !== '') {
            const task = document.createElement('li');
            task.innerText = taskInput.value;

            // Add a button to mark task as complete
            const completeButton = document.createElement('button');
            completeButton.innerText = 'Complete';
            completeButton.onclick = function() {
                task.classList.toggle('completed');
            };

            // Add a button to delete task
            const deleteButton = document.createElement('button');
            deleteButton.innerText = 'Delete';
            deleteButton.onclick = function() {
                task.remove();
            };

            task.appendChild(completeButton);
            task.appendChild(deleteButton);

            taskList.appendChild(task);
            taskInput.value = ''; // Clear the input field
        }
    }
</script>

</body>
</html>

