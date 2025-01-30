<template>
    <div id="app-body">
        <div class="container">
            <h2>Input Todo Here:</h2>
            <form>
            <span class="inline-form-group row">
                <input v-model.trim="todoInput" type="text" id="todo-input" class="form-control" name="todo-input" minlength="10" maxlength="25" placeholder="Todo...">
                <button id="submitTodo" type="button" class="col-1 btn btn-primary" @click="addTodo">Submit</button>
            </span>
        </form>
        </div>
        <div class="list-group">
            <li class="list-item container" v-for="item in listItems">
                <span class="list-info row">
                    <span class="col-6">{{ item.message }}</span>
                    <span class="col-3">{{ item.timeStamp }}</span>
                    <button class="col-1 list-close btn btn-danger" type="button" @click="removeTodo(item)">X</button>
                </span>
            </li>
        </div>

        <button v-if="checkedListItems.length > 0" @click="bulkRemove(checkedListItems)" type="button">Remove All</button>
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
                        timeStamp: 
                    }
                )
            },
            removeTodo(todo) {
                const result = this.listItems.filter((item) => item != todo)
                this.listItems = result
            },
            bulkRemove(items) {
                console.dir(items)
            }
        }
    }
</script>

<style scoped>
    #app-body {
        border: 5px solid #26292C;
        /*border-radius: 5%;
        margin: 2% 35%;
        max-width: 27vw;
        min-height: 75vh;*/
        padding: 1.5%;
    }
    
    h2 {
        font: 1.5rem "Calibri", sans-serif;
    }

    .list-item {
        border-radius: 5.5px;
        list-style-type: none;
        max-width: 96%;
        margin: 2%;
        padding: 2%;
    }

    .list-close {
        background-image: linear-gradient(#A20202, #D60202);
        margin-left: 12%;
    }

    #todo-input {
        margin-top: 10%;
        min-width: 85%;
    }

</style>