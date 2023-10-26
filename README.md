# Javascript-Aplicaci-n-de-Tareas
Crear una aplicación de tareas en JavaScript es un proyecto popular para ayudarte a gestionar tus tareas diarias. A continuación, te proporcionaré un ejemplo básico de una aplicación de tareas que utiliza HTML, CSS y JavaScript:

1. **HTML**:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Lista de Tareas</title>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
    <h1>Lista de Tareas</h1>
    <div id="task-list">
        <input type="text" id="task-input" placeholder="Agregar una nueva tarea">
        <button id="add-task">Agregar</button>
        <ul id="tasks"></ul>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

2. **CSS** (Guárdalo en un archivo llamado `styles.css`):

```css
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: #f9f9f9;
}

h1 {
    color: #333;
}

#task-list {
    width: 60%;
    margin: 20px auto;
    padding: 20px;
    background-color: #fff;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 5px #ccc;
}

#task-input {
    width: 70%;
    padding: 10px;
    margin-right: 10px;
    font-size: 16px;
}

#add-task {
    background-color: #333;
    color: #fff;
    font-size: 16px;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 5px 0;
    background-color: #f9f9f9;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

li button {
    background-color: #f44336;
    color: #fff;
    font-size: 14px;
    padding: 5px 10px;
    border: none;
    cursor: pointer;
}
```

3. **JavaScript** (Guárdalo en un archivo llamado `script.js`):

```javascript
document.addEventListener('DOMContentLoaded', function () {
    const taskInput = document.getElementById('task-input');
    const addTaskButton = document.getElementById('add-task');
    const taskList = document.getElementById('tasks');

    addTaskButton.addEventListener('click', function () {
        const taskText = taskInput.value.trim();
        if (taskText !== '') {
            const taskItem = document.createElement('li');
            taskItem.innerHTML = `
                ${taskText}
                <button class="delete-task">Eliminar</button>
            `;
            taskList.appendChild(taskItem);

            taskInput.value = ''; // Limpiar el campo de entrada

            const deleteButtons = document.querySelectorAll('.delete-task');
            deleteButtons.forEach(button => {
                button.addEventListener('click', function () {
                    taskList.removeChild(taskItem);
                });
            });
        }
    });

    taskInput.addEventListener('keydown', function (e) {
        if (e.key === 'Enter') {
            addTaskButton.click();
        }
    });
});
```

Este es un ejemplo básico de una aplicación de tareas que te permite agregar tareas, marcarlas como completadas y eliminarlas. Puedes personalizar y expandir la funcionalidad según tus necesidades, como agregar fechas de vencimiento, categorías de tareas, etc. También puedes considerar el uso de librerías y frameworks de JavaScript, como React o Vue.js, para desarrollar aplicaciones de tareas más complejas y dinámicas.
