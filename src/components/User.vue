<script>
    export default {
        props: {
            user: {
                type: Object,
                required: true
            },
            index: {
                type: Number,
                required: true
            },
            deleteUser: {
                type: Function,
                required: true
            }
        }
    }
</script>


<template>
    <div className="user">
      <div className="user__button-container">  
        <button @click="deleteUser(index)">x</button> 
      </div> 
      <h3>{{ user.name }}</h3>
      <p>{{ user.email }} - <b>{{ user.pass }}</b></p>
    </div>
</template>


<style scoped>
    .user {
        padding: 10px;
        background-color: #cfcdff;
    }

    .user__button-container {
        display: flex;
        flex-direction: row-reverse;
    }

    button {
        background-color: #9e7eff;
        border: 1px solid #57539f;
        color: #25216e;
        font-size: 13px;
    }
</style>