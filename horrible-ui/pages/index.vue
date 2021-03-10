<template>
  <div class="container">
    <div>
      <div
        class="bg-white shadow-lg rounded px-8 pt-6 pb-8 mb-4 flex flex-col"
        id="form"
      >
        <div class="flex justify-start items-start mb-3">
          <img class="w-12 h-12 mr-1" src="../static/logo.png"/>
          <label class="text-xl text-grey-darker font-bold my-auto mb-2 flex">
            {{ title }}
          </label>
        </div>
        <div class="mb-4">
          <label class="block text-grey-darker text-sm font-bold mb-2" for="username">
            Username
          </label>
          <span class="flex justify-start items-start">
            <input v-model="userName" disabled="disabled" class="shadow appearance-none border rounded w-full py-2 px-3 text-grey-darker" id="username" type="text" placeholder="Username">
            <button
              class="w-48 bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
              @click="generateUsername(Math.floor(Math.random() * (20 - 4 + 1)) + 4)"
            >
              Username
            </button>
          </span>
        </div>
        <div class="mb-2">
          <label class="block text-grey-darker text-sm font-bold mb-2" for="password">
            Password
          </label>
          <span class="flex justify-start items-start">
            <input v-model="passWord" disabled="disabled" class="shadow appearance-none border border-red rounded w-full py-2 px-3 text-grey-darker mb-3" id="password" type="password" placeholder="******************">
            <button
              class="w-48 bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
              @click="generatePassword(Math.floor(Math.random() * (16 - 8 + 1)) + 8)"
            >
              Password
            </button>
          </span>
        </div>
        <div class="mb-2">
          <label class="block text-grey-darker text-sm font-bold mb-2" for="password">
            Personal ID Code
          </label>
          <span class="flex justify-start items-start">
            <input v-model="idCode" disabled="disabled" class="shadow appearance-none border border-red rounded w-full py-2 px-3 text-grey-darker mb-3" id="id-number" type="number" placeholder="55555555555">
            <button 
              class="w-48 bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
              @click="generateIdCode()"
            >
              Personal ID
            </button>
          </span>
        </div>

        <label class="flex justify-start items-start">
          <div class="bg-white rounded w-6 h-6 flex flex-shrink-0 justify-center items-center mr-2 focus-within:border-blue-500">
            <input type="checkbox" class="form-checkbox w-5 h-5">
          </div>
          <div class="select-none">Remember username</div>
        </label>
        <div class="flex items-center justify-end">
          <a class="inline-block align-baseline font-bold text-sm text-blue hover:text-blue-darker mx-4" href="/#">
            Forgot Password?
          </a>
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
            Sign In
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Tetra Identification Center',
      userName: '',
      passWord: '',
      idCode: '',
    }
  },
  methods: {
    generateUsername(length) {
      this.userName = '';
      var characters = 'ABCDEFGHIJKLMNOPRSTUVabcdefghijklmnopqrstuv';
      for ( var i = 0; i < length; i++ ) {
          this.userName += characters.charAt(Math.floor(Math.random() * characters.length));
      }
    },

    generatePassword(length) {
      this.passWord = '';
      var characters = 'PQRSTUVWXYZpqrstuvwxyz0123456789!@#$%&*';
      for ( var i = 0; i < length; i++ ) {
          this.passWord += characters.charAt(Math.floor(Math.random() * characters.length));
      }
    },

    generateIdCode() {
      this.idCode = '';
      var characters = '0123456789';
      for ( var i = 0; i < 11; i++ ) {
          this.idCode += characters.charAt(Math.floor(Math.random() * characters.length));
      }
    },
  }
}
</script>

<style>
.container {
  width: 100vh;
  height: 100vh;
  margin: 25vh auto;
}

#form {
  width: 45vh;
  margin: 0 auto;
}
</style>
