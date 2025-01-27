<template>
    <div id="app-body">
        <h2>Input Todo Here: {{ todoInput }}</h2>
        <div>
            <form>
            <span class="inline-form-group">
                <input v-model.trim="todoInput" type="text" id="todoInput" name="todoInput" minlength="10" maxlength="25" placeholder="Todo...">
                <button id="submitTodo" type="button" @click="addTodo">Submit</button>
            </span>
        </form>
        </div>
        <div class="list-group">
            <li class="list-item" v-for="(item, index) in items">
                <span class="list-info">
                    {{ item.id }}
                    {{ item.message }}
                    {{ item.timeStamp }}
                    <button class="listControl" type="button" @click="removeTodo(item.id)">X</button>
                </span>
            </li>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                todoInput: "",
                timeStamp: "",
                listItems: [],
                checkedListItems: []
            }
        },
        methods: {
            addTodo() {
                console.log("Did not code logic yet!")
            },
            removeTodo() {
                console.log("This feature has not be coded yet!")
            },
            bulkRemove() {
                console.log("This has not been implemented yet!")
            }
        }
    }
</script>

<style scoped>
    #app-body {
        border: 5px solid #26292C;
        border-radius: 5%;
        margin: 2% 35%;
        max-width: 27vw;
        min-height: 75vh;
        padding: 1.5%;
    }
</style>