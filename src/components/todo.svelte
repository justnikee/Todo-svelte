<script>
    const heading = 'Todo App'

    // import AddTodo from "./addTodo.svelte";

    let todos = [
        { id: '1e4a59703af84', text: 'Todo 1', completed: true },
    { id: '9e09bcd7b9349', text: 'Todo 2', completed: false },
    { id: '9e4273a51a37c', text: 'Todo 3', completed: false },
    { id: '53ae48bf605cc', text: 'Todo 4', completed: false },
    ]

//     $: todosAmount = todos.length

//     const generateRandomId = () => {
//         return Math.random.toString(16).slice(2)
//     }

//     const addTodo = (todo) => {
//         let newTodo = {
//             id: generateRandomId(),
//             text: todo,
//             completed: false
//         }

//         todos = [...todos, newTodo]
//     }

//     function toggleCompleted(event) {
//     let { checked } = event.target as HTMLInputElement

//     todos = todos.map((todo) => ({
//       ...todo,
//       completed: checked,
//     }))
//   }


</script>

<div class="todo-container">
    <div class="todo-top-area">
        <h1 class="todo__heading">
            {heading}
        </h1>
    </div>
    <div class="todos">
        <form>
            <input type="text" 
            id="new-todo"
            class="todo-input"
            placeholder="What Needs To Be Done"
            autofocus
            >

            <input type="checkbox" 
            id="new-checkbox"
            class="todo-checkbox"
            >
            <label for="new-checkbox">Mark all as complete</label>
        </form>
        <ul>
            {#each todos as todo (todo.id) }
            <li>
                <div class="todo-items">
                    <input type="checkbox" class="edit-box" id="edit-checkbox" checked={todo.completed} />
                    <lable for="edit-checkbox" />
                </div>
                <span class="todo-list-item">{todo.text}</span>
                <button class="remove-button" />
            </li>
            {/each}
        </ul>

        <div class="actions">
            <span class="task-count">0</span>
            <div class="filter-task">
                <button class="filter-all">All</button>
                <button class="filter-active">Active</button>
                <button class="filter-completed">Completed</button>
            </div>
            <button class="clear-all">Clear all</button>
        </div>
    </div>
</div>