<template>
  <div>
    <h2>Manage Goals</h2>
    <input type="text" ref="goal" />
    <button @click="setGoal">Set Goal</button>
    <teleport to="#app">
      <error-alert v-if="isError">
        <p>Wrong</p>
        <button @click="confirmError">Ok</button>
      </error-alert>
    </teleport>
  </div>
</template>
<script>
import ErrorAlert from "./ErrorAlert";
export default {
  data() {
    return {
      isError: false,
    };
  },
  components: {
    ErrorAlert,
  },
  methods: {
    setGoal() {
      const enteredValue = this.$refs.goal.value;
      if (!enteredValue) this.isError = true;
      else this.isError = false;
    },
    confirmError() {
      this.isError = false;
    },
  },
};
</script>