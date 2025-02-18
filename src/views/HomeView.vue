<script setup lang="ts">
import InputBox from '@/components/reuseables/InputBox.vue';
import ButtonDiv from '@/components/reuseables/ButtonDiv.vue';
import { ref } from 'vue';
const emailValue = ref('');
const passwordValue = ref('');
</script>

<template>
  <main class="main_div">
    <div class="logo_div">
      <img src="/logo.png" class="" />
    </div>
    <div class="left_section">
      <div class="left_section_content">

        <div class="poster">
          <img src="/image.jpg" class="m-auto" />
          <p class="achieve header">Team Achieve</p>
          <p class="subtext">Your perfect solution for funding your desires</p>
        </div>
      </div>
    </div>
    <div class="right_section">
      <div class="right_section_content">
        <p class="header welcome">Welcome Back</p>
        <p class="welcome subtext">Enter your email address and password to access your account.</p>
        <div class="form">
          <div class="input_box">
            <InputBox name="email" v-model="emailValue" label="Email Address" placeholder="Enter your email"
              required />
          </div>
          <div class="input_box">
            <InputBox name="password" v-model="passwordValue" label="Password" placeholder="Enter your password"
              required />
          </div>
          <div class="remember_me">
            <div class="checkbox">
              <input type="checkbox" id="checkbox" />
              <label class="pl-3" for="checkbox">Remember Me</label>
            </div>
            <p class="">Forgot Password?</p>
          </div>
          <div class="button_sign_in">
            <ButtonDiv name="Sign in" />
          </div>
        </div>
        <div class="register">
          <p class="subtext">Don't have an account?</p>
          <p class="sign_up">Sign up</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.remember_me {
  padding: 0px 10px;
}

.remember_me,
.remember_me .checkbox {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 10px;
}
.remember_me .checkbox {
  padding: 0px;
  gap: 4px;
}

.remember_me label {
  padding-left: 0px;
  color: #5E5E5E;
  cursor: pointer;
}

.remember_me p,
.sign_up {
  color: #61227D;
}
.button_sign_in{
  padding-top: 40px;
}
/* Form */
.form {
  width: 100%;
  padding-bottom: 15px;
}
.header.welcome{
  font-size: 2em;
  font-family: "Lora", serif;
  padding-bottom: 5px;
}

.subtext.welcome{
  font-weight: normal;
  font-size: 1em;
  padding-bottom: 20px;
}
.form .input_div {
  padding: 15px 0px;
}

.register {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}

.sign_up {
  padding-left: 10px;
  font-weight: 600;
  font-size: 15px;
}

@media screen and (max-width: 400px) {
  .header.welcome{
    font-size: 1.4em;
  }
}
</style>
