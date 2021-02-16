<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="buttons">
      <button class="button primary" @click="loading = !loading">
        <img v-if="loading" alt="loading" class="loading" src="../assets/loading.svg"/>
        <p v-else>Button</p>
      </button>
      <button disabled class="button primary">Button</button>
    </div>
    <div class="buttons">
      <button class="button secondary" @click="loading = !loading">
        <img v-if="loading" alt="loading" class="loading" src="../assets/loading2.svg"/>
        <p v-else>Button</p>
      </button>
      <button disabled class="button secondary">Button</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Buttons',
  data() {
    return {
      loading: false
    }
  },
  props: {
    msg: String
  }
}
</script>

<style scoped>
.hello {
  display: flex;
  flex-direction: column;
}

.buttons {
  display: flex;
  justify-content: space-around;
  margin-bottom: 6vh;
}

.button {
  display: flex;
  justify-content: center;
  align-items: center;
  border: none;
  padding: 2vh;
  border-radius: 1vh;
  height: 6vh;
  width: 12vh;
  font-weight: bold;
  font-size: 2vh;
}

.primary {
  background-color: #5f2eea;
  color: white;
}

.secondary {
  background-color: white;
  color: #5f2eea;
  border: #5f2eea 2px solid;
}

.primary:hover {
  background-color: #2a00a2;
  transition: .3s;
}

.secondary:hover {
  color: #2a00a2;
  border: #2a00a2 2px solid;
  transition: .3s;
}

.button:focus {
  outline: none !important;
  box-shadow: 0 0 2vh #2a00a2;
}

.primary:disabled {
  background-color: #af97f4;
}

.secondary:disabled {
  color: #af97f4;
  border: #af97f4 2px solid;
}

.loading {
  animation: rotation 2s infinite linear;
  height: 3vh;
}

@keyframes rotation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(359deg);
  }
}
</style>
