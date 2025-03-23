<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Study Planner App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            background: #f4f4f4;
        }
        .container {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            color: #333;
        }
        p {
            color: #555;
        }
        input, select, textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            background: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Study Planner App</h1>
        <p>Organize your tasks, set deadlines, and track progress easily.</p>
        
        <form id="plannerForm">
            <label for="task">Task Name:</label>
            <input type="text" id="task" name="task" placeholder="Enter task name" required>
            
            <label for="deadline">Deadline:</label>
            <input type="date" id="deadline" name="deadline" required>
            
            <label for="priority">Priority:</label>
            <select id="priority" name="priority">
                <option value="High">High</option>
                <option value="Medium">Medium</option>
                <option value="Low">Low</option>
            </select>
            
            <button type="submit">Add Task</button>
        </form>
        
        <h2>Task List</h2>
        <ul id="taskList"></ul>
    </div>

    <script>
        document.getElementById('plannerForm').addEventListener('submit', function(event) {
            event.preventDefault();
            
            let task = document.getElementById('task').value;
            let deadline = document.getElementById('deadline').value;
            let priority = document.getElementById('priority').value;
            
            let taskList = document.getElementById('taskList');
            let listItem = document.createElement('li');
            listItem.textContent = `${task} - ${deadline} (${priority})`;
            taskList.appendChild(listItem);
            
            document.getElementById('plannerForm').reset();
        });
    </script>
</body>
</html>
