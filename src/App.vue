<template>
  <div>
    <child :object="object"></child>
    <div> {{ message }} </div>
    <div v-bind:class="{ active: isActive }"> {{ message2 }} </div>
    <button v-on:click="reverse">Reverse</button>
    <div v-bind:class="[ { active: isActive }, errorClass]"></div>
    <count_button></count_button>
    <count_button></count_button>
    <count_button></count_button>
    <h1 v-if="awesome">Vue is awesome!</h1>
    <h1 v-else>Oh no 😢</h1>
    <template v-if="loginType === 'username'">
      <label>
        Username
      </label>
      <input placeholder="username" key="username-input">
    </template>
    <template v-else>
      <label>
        Email
      </label>
      <input placeholder="email" key="username-email">
    </template>
    <button v-on:click="changeLoginType">ChangeLoginType</button>
  </div>
</template>

<script>
import child from './components/child'
import count_button from './components/CountButton'

export default {
  components: {
    child,
    count_button
  },
  data () {
    return {
      message: 'Hello Vue!!',
      message2: '12345',
      isActive: 'active',
      errorClass: 'text-danger',
      awesome: true,
      loginType: false,
      object: {
        title: 'How to do lists in Vue',
        publishedAt: '2016-04-10',
        authors: [
          { name: 'Jane Doe' },
          { name: 'Jane Doe2' },
        ]
      }
    }
  },
  computed: {
    classObject: function () {
      return {
        active: this.isActive && !this.error,
        'text-danger': this.error && this.error.type === 'fatal'
      }
    }
  },
  methods: {
    reverse: function() {
      this.message2 = this.message2.split("").reverse().join("");
    },
    changeLoginType: function(){
      this.loginType = this.loginType === 'username' ? 'email' : 'username'
    }
  }
}
</script>
