<script>
import User from './components/User.vue';

export default {
  components: { User },
  data() {
    return {
      users: [],
      error: '',
      userName: '',
      userPass: '',
      userEmail: ''
    }
  }, 
  methods: {
    sendData() {
      if (this.userName == '') {
        this.error = 'Имя не введено';
        return;
      } else if (this.userEmail == '') {
        this.error = 'Адрес не введён'
        return
      } else if (this.userPass == '') {
        this.error = 'Пароль не введён'
        return
      }

      this.error = '';

      this.users.push({
        name: this.userName,
        pass: this.userPass,
        email: this.userEmail

      })
    },
    deleteUser(index) {
      this.users.splice(index, 1);
    }
  }
}
</script>

<template>
  <main className="main">
    <form>
      <h2 className="form__title">Форма</h2>
      <input className="form__input" type="text" v-model="userName" placeholder="Имя"/>
      <input className="form__input" type="password" v-model="userPass" placeholder="Пароль"/>
      <input className="form__input" type="email" v-model="userEmail" placeholder="Email"/>
      <button type="button" @click="sendData()">Отправить</button>
      <p className="error">{{ error }}</p>
    </form>
    
    <User v-for="(el, index) in users" :key="index" :user="el" :index="index" :deleteUser="deleteUser"/>
  </main>
</template>

<style scoped>
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 600px;
}

form {
  display: flex;
  flex-direction: column;
}

.form__title {
display: flex;
justify-content: center;
font-family: math;
}

.form__input {
  width: 300px;
  height: 50px;
  margin: 0 0 10px;
  padding: 0 0 0 10px;
  font-family: math;
  font-size: 16px;
}

button {
  border: 1px solid #1da654;
  height: 54px;
  border-radius: 2px;
  background-color: #5bf080;
  font-family: math;
  font-size: 19px;
  color: #326856;
}

.error {
  color: red;
}
</style>
