<script>
export default {
  data() {
    return {
      info: 'Title!',
      someInfo: 'Anons of message'
    }
  }, 
  methods: {
    userData(param) {
      //this.someInfo = 'Some new'
      this.info = param
    }
  }
}
</script>

<template>
  <h3>{{ info }}</h3>
  <p>{{ someInfo }}</p>

  <button type="button" @click="userData('Some new')">Отправить</button>
</template>

<style scoped>

h3 {
  font-weight: lighter;
}

p {
  color: red;
}

</style>
