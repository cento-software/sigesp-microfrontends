<script setup lang="ts">
import { reactive, ref } from 'vue';

const errorMessage = ref("")
const loginData = reactive({
  username: "",
  password: ""
})

const onSubmit = (ev: Event) => {
  ev.preventDefault();
  errorMessage.value = "";

  if (loginData.username !== "admin" || loginData.password !== "admin") {
    errorMessage.value = "Usuário ou senha incorretos"
    return;
  }

  window.location.href = "/modulos"
}
</script>

<template>
  <form @submit="onSubmit">
    <div v-if="errorMessage" class="alert-error">
      {{ errorMessage }}
    </div>

    <input name="username" required type="text" placeholder="Usuário" v-model="loginData.username" />
    <input name="password" required type="password" placeholder="Senha" v-model="loginData.password" />
    <div class="buttons">
      <button id="login" type="submit">Logar</button>
      <button id="password-reset">Esqueci minha senha</button>
    </div>
  </form>
</template>

<style scoped>
form {
  background-color: white;
  border-radius: 0.5rem;
  width: 400px;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 1.5rem;
}

.alert-error {
  padding: 1rem;
  font-size: .9rem;
  text-align: center;
  border: 1px solid #f9d7d3;
  border-radius: .25rem;
  background-color: #fbe2e0;
  color: #7a3a33;
}

input,
button {
  padding: 0.5rem;
  border-radius: 0.25rem;
}

.buttons {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

</style>
