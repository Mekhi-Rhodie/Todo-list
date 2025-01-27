<template>
    <div id="app-body">
        <h2>Input Todo Here</h2>
        <div>
            <form>
            <span class="inline-form-group">
                <input v-model.trim="todoInput" type="text" id="todoInput" name="todoInput" minlength="10" maxlength="25" placeholder="Todo...">
                <button id="submitTodo" type="button" @click="addTodo">Submit</button>
            </span>
        </form>
        </div>
        <div class="list-group">
            <li class="list-item" v-for="item in listItems">
                <span class="list-info">
                    <input type="checkbox" v-model="checkedListItems">
                    {{ item.message }}
                    {{ item.timeStamp }}
                    <button class="list-close" type="button" @click="removeTodo(item)">X</button>
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
                this.listItems.push(
                    {
                        id: this.listItems.length + 1,
                        message: this.todoInput,
                        timeStamp: "\'Current Date\''"
                    }
                )
            },
            removeTodo(todo) {
                const result = this.listItems.filter((item) => item != todo)
                this.listItems = result
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

    .list-item {
        border: .5px solid #02C77C;
        border-radius: 5.5px;
        list-style-type: none;
        margin: 2%;
        max-width: 80%;
        padding: 2%;
    }

    .list-close {
        background-image: linear-gradient(#A20202, #D60202);
        margin-left: 12%;
    }
</style>