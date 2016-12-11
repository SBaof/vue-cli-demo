<style>

#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /*text-align: center;*/
    color: #2c3e50;
    margin-top: 60px;
}

</style>

<template>

<div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <hello></hello> -->

    <nav class="navbar navbar-static-top navbar-default"></nav>
    <div class="container" id="app">
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <div class="panel panel-default">
                    <div class="panel-heading">VueJs 2.0</div>
                    <div class="panel-body">
                        <todo :todos="todos"></todo>
                        <todo-form :todos="todos"></todo-form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

</template>

<script>

import Hello from './components/Hello'
import Todo from './components/Todo'
import TodoForm from './components/TodoForm'

export default {
    name: 'app',
    data() {
        return {
            todos: [{
                id: 1,
                title: 'PHP: The BEST language in the world!',
                complete: false,
            }, {
                id: 2,
                title: 'Laravel: The framework for web artisans',
                complete: false,
            }],
            todox: [{
                id: 1,
                title: 'PHP: The BEST language in the world!',
                complete: false,
            }, {
                id: 2,
                title: 'Laravel: The framework for web artisans',
                complete: false,
            }],
        }
    },
    components: {
        Hello, Todo, TodoForm
    }
}

</script>
