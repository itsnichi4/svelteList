<script>
  let newItem = '';

  let todoList = [{text: 'task1', checked: true},
                  {text: 'task2', checked: false},
                  {text: 'task3', checked: false}];

function addToList() {
  todoList = [...todoList, {text: newItem, checked: false}];
  newItem = '';
}

function removeFromList(index) {
  todoList.splice(index, 1)
  todoList = todoList;
  }
</script>

<input bind:value={newItem} type="text" placeholder="new todo item..">
<button on:click={addToList}>Add</button>

<br/>
{#each todoList as item, index}

<input bind:checked={item.checked} type="checkbox">
<span class:checked={item.checked}>{item.text}</span>
<button on:click={() => removeFromList(index)}>remove</button>
<br/>

{/each} 



<style>
	.checked {
        text-decoration: line-through;
    }
</style>
