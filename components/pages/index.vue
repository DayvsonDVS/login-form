<template>
  <div class="box">
    <div class="form">
      <h2>Sing in</h2>
      <div class="inputBox">
        <input type="text" required="true" />
        <span>Username</span>
        <i></i>
      </div>

      <div class="inputBox">
        <input type="password" required="true" />
        <span>Password</span>
        <i></i>
      </div>

      <div class="links">
        <a href="#">Forgot Password</a>
        <a href="#">Sing up</a>
      </div>
      <input type="submit" value="Login" />
    </div>
  </div>
</template>

<script setup lang="ts">
import '/assets/scss/main.scss'
</script>

<style scoped lang="scss">
.box {
  background: #1c1c1c;
  border-radius: 8px;
  height: 400px;
  overflow: hidden;
  position: relative;
  width: 300px;
  &::before {
    animation: animate 6s linear infinite;
    background: linear-gradient(0deg, transparent, #45f3ff, #45f3ff);
    content: '';
    height: 400px;
    left: -50%;
    position: absolute;
    top: -50%;
    transform-origin: bottom right;
    width: 300px;
  }
  &::after {
    background: linear-gradient(0deg, transparent, #45f3ff, #45f3ff);
    content: '';
    height: 400px;
    position: absolute;
    left: -50%;
    top: -50%;
    width: 300px;
    animation: animate 6s linear infinite;
    transform-origin: bottom right;
    animation-delay: -3s;
  }
  @keyframes animate {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  .form {
    background: #28292d;
    border-radius: 8px;
    inset: 2px;
    position: absolute;
    z-index: 10;
    padding: 50px 40px;
    display: flex;
    flex-direction: column;

    h2 {
      color: #45f3ff;
      font-weight: 500;
      text-align: center;
      letter-spacing: 0.1em;
    }
  }
  .inputBox {
    position: relative;
    width: 210px;
    margin-top: 35px;
    input {
      background: transparent;
      border: none;
      color: #23242a;
      font-size: 1em;
      letter-spacing: 0.05em;
      outline: none;
      padding: 20px 10px 10px;
      position: relative;
      width: 100%;
      z-index: 10;
    }
    span {
      color: #8f8f8f;
      font-size: 1em;
      left: 0;
      letter-spacing: 0.5em;
      padding: 20px 0px 10px;
      pointer-events: none;
      position: absolute;
      transition: 0.5s;
    }
    i {
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100%;
      height: 2px;
      background: #45f3ff;
      border-radius: 4px;
      transition: 0.5s;
      pointer-events: none;
      z-index: 9;
    }
  }
  .inputBox input:valid ~ span,
  .inputBox input:focus ~ span {
    color: #45f3ff;
    transform: translateX(0px) translateY(-34px);
    font-size: 0.75em;
  }
  .inputBox input:valid ~ i,
  .inputBox input:focus ~ i {
    height: 44px;
    pointer-events: none;
  }

  .links {
    display: flex;
    justify-content: space-between;
    a {
      margin: 10px 0;
      font-size: 0.75em;
      color: #8f8f8f;
      text-decoration: none;
      &:hover {
        color: #45f3ff;
      }
      &:nth-child(2) {
        color: #45f3ff;
      }
    }
  }
  input[type='submit'] {
    border: none;
    outline: none;
    background: #45f3ff;
    padding: 11px 25px;
    width: 100px;
    margin-top: 10px;
    border-radius: 4px;
    font-weight: 600;
    cursor: pointer;
    &:active {
      opacity: 0.8;
    }
  }
}
</style>
