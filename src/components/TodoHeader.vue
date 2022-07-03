<template>
  <header class="header">
    <h1>todos</h1>
    <input id="toggle-all" class="toggle-all" type="checkbox" />
    <label for="toggle-all"></label>
    <!-- label 可以关联一个表单标签 -->
    <input
      class="new-todo"
      placeholder="输入任务名称-回车确认"
      autofocus
      v-model.trim="val"
      @keydown.enter="enter"
    />
  </header>
</template>

<script>
export default {
  data() {
    return {
      val: "",
    };
  },
  methods: {
    enter() {
      if (this.val.length == 0) {
        alert("请重新输入");
        return ;
      }
      this.$emit("enters", this.val);
      this.val = "";
    },
  },
};
</script>