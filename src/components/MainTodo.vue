<script setup>
import {ref} from 'vue';
import { useTodoList } from '/src/composables/useTodoList.js';

const todoRef = ref('');
const isEditRef = ref(false);
const { todoListRef, add, show, edit, del, check } = useTodoList();

const addTodo = () => {
  add(todoRef.value);
  todoRef.value = '';
};

const showTodo = (id) => {
  todoRef.value = show(id);
  isEditRef.value = true;
};

const editTodo = () => {
  edit(todoRef.value);
  isEditRef.value = false;
  todoRef.value = '';
};

const deleteTodo = (id) => {
  del(id);
};

const changeCheck = (id) => {
  check(id);
};
</script>

<template>
  <div class="box-input">
    <input type="text" class="todo-input" placeholder="+ TODOを入力" v-model="todoRef" />
    <button class="btn green" @click="editTodo" v-if="isEditRef">変更</button>
    <button class="btn" @click="addTodo" v-else>追加</button>
  </div>
  <div class="box-list">
    <div class="todo-list" v-for="todo in todoListRef" :key="todo.id">
      <div class="todo" :class="{ fin: todo.checked }">
        <input type="checkbox" class="check" @change="changeCheck(todo.id)" :checked="todo.checked" /><label>{{ todo.task }}</label>
      </div>
      <div class="btns">
        <button class="btn green" @click="showTodo(todo.id)">編</button>
        <button class="btn pink" @click="deleteTodo(todo.id)">削</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.box-input {
  margin-top: 20px;
}

.todo-input {
  width: 300px;
  margin-right: 8px;
  padding: 8px;
  font-size: 18px;
  border: 1px solid #fff;
  border-radius: 6px;
}
.btn {
  padding: 8px;
  background-image: linear-gradient(-20deg, #616161 0%, #9bc5c3 100%);
  border-radius: 6px;
  color: #fff;
  text-align: center;
  font-size: 14px;
}
.box-list {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.todo-list {
  display: flex;
  align-items: center;
  gap: 8px;
}
.todo {
  border: 1px solid #fff;
  border-radius: 6px;
  padding: 12px;
  width: 300px;
}
.check {
  border: 1px solid red;
  transform: scale(1.6);
  margin: 0 16px 2px 6px;
}
.btns {
  display: flex;
  gap: 4px;
}
.green {
  background: #00A7E1;
}
.pink {
  background: #EF6461;
}

.fin {
  text-decoration: line-through;
  background-color: #fff;
  color: #333;
}
</style>
