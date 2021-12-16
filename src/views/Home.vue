<template>
  <div class="home">
    <h1 class="title">初めてのTODOアプリ</h1>
    <div class="card">
      <h2 class="card-title">タスクを追加</h2>
      <div class="add-task">
        <input
          v-model="newTask"
          class="input"
          type="text"
          placeholder="タスクを入力"
        />
        <v-button @click="addTask" />
      </div>
    </div>
    <div class="card">
      <h2 class="card-title">完了済みタスク</h2>
      <div class="task">
        <label class="task-left" for="">
          <input type="checkbox" name="" id="" />
          <p class="task-name">髪切る</p>
        </label>
        <v-button />
      </div>
    </div>
    <div class="card">
      <h2 class="card-title">未完了タスク</h2>
      <div class="task">
        <label class="task-left" for="">
          <input type="checkbox" name="" id="" />
          <p class="task-name">髪切る</p>
        </label>
        <v-button />
      </div>
    </div>
    <div class="card">
      <h2 class="card-title">全てのタスク</h2>
      <div v-for="(task, index) in taskList" :key="index" class="task">
        <label class="task-left" for="">
          <input v-model="task.done" type="checkbox" name="" id="" />
          <p class="task-name">{{ task.name }}</p>
        </label>
        <v-button />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import VButton from "@/components/VButton.vue";

export default {
  name: "Home",
  components: {
    VButton,
  },
  data() {
    return {
      newTask: "",
      taskList: [
        { name: "test1", done: true },
        { name: "test2", done: false },
        { name: "test3", done: true },
      ],
    };
  },
  methods: {
    addTask() {
      console.log("add");
    },
  },
};
</script>

<style scoped>
.add-task {
  display: flex;
  width: 100%;
}
.input {
  border: 1px solid #dddddd;
  border-radius: 4px;
  padding: 5px;
  flex-grow: 1;
  flex-shrink: 1;
  margin-right: 10px;
}
.title {
  font-size: 1.8rem;
  font-weight: bold;
  margin-top: 1rem;
  margin-bottom: 1rem;
}
.card-title {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 0.8rem;
}
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #f5faf5;
  min-height: 100vh;
}
.task {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.task-left {
  display: flex;
  align-items: center;
}
.task-name {
  margin-left: 10px;
}
.card {
  background: white;
  padding: 12px;
  box-shadow: 0px 4px 5px 0px rgba(0, 0, 0, 0.3);
  border-radius: 8px;
  margin-bottom: 16px;
  width: 300px;
}
</style>
