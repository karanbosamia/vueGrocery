<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
    <div class="box-form">
    <div class="left">
        <div class="overlay">
            <h1>Grocery Store</h1>
        </div>
    </div>

    <div class="right">
        <h4>Login</h4>
        <br/>
        <br/>
        <br/>
        <p>Don't have an account? <a href="/register">Create Your Account</a> it takes less than a minute</p>
        <div class="inputs">
            <input  v-model="username" type="text" placeholder="Username">
            <br>
            <input v-model="password" type="password" placeholder="Password">
        </div>
            <br><br>
        <div class="remember-me--forget-password">
            <label>
                <input type="checkbox" name="item" checked/>
                <span class="text-checkbox">Remember me</span>
            </label>
        </div>
        <br>
        <div>
            <p>Forgot password?</p>
        </div>
            <br>
            <button @click="sendData">Login</button>
        </div>
    </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>

<script>
export default {
  props: {
    username: {
      type: String,
      required: true
    },
    password: {
      type: String,
      required: true
    }
  },
  setup(props) {

    const sendData = () => {
      const data = {
        username: props.username,
        password: props.password
      };
    };

    return {
      sendData
    };
  }
};
</script>