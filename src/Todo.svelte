<script>
    let taskList = [];
    let newTaskValue = "";
    function addToList() {
        taskList.push(newTaskValue);
        taskList = taskList;
        for (let i = 0; i < taskList.length; i++) {
            console.log(taskList[i]);
        }
        newTaskValue = "";
    }
</script>

<div class="h-auto w-80 flex flex-col border-2">
    <div class="">TODO</div>
    <div class="flex flex-row justify-center items-center border-2 m-1 p-1">
        <input
            bind:value={newTaskValue}
            type="text"
            placeholder="Add your task "
            class="border-none p-1"
        />
        <button
            on:click={addToList}
            class="h-7 w-7 border-none justify-center items-center">+</button
        >
    </div>
    <div class="h-auto w-full border-2 flex flex-col mt-4 p-2">
        {#each taskList as task, index}
            <div class="flex flex-row ">
                <input type="checkbox" class="m-1 " />
                <div type="text" class="border-2 text-red-900 m-1">{task}</div>
                <div>x</div>
            </div>
        {/each}
    </div>
</div>
