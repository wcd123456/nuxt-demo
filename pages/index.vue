<template>
  <div class="container">
    <p>邮箱： <input v-model="username" type="text" /></p>
    <p>密码： <input v-model="password" type="text" /></p>
    <p>图片验证： <input v-model="code" type="text" /></p>
    <p>sid: <input v-model="sid" type="text" /></p>
    <button type="button" @click="login()">登录</button>
  </div>
</template>

<script>
export default {
  // async asyncData({ $axios }) {
  //   const result = await $axios.get('http://localhost:8000/posts')
  //   return {
  //     posts: result
  //   }
  //   // ErrorHandle($axios, redirect)
  // },
  data() {
    return {
      username: '',
      password: '',
      code: '',
      sid: '',
    }
  },
  mounted() {
    window.vue = this
  },
  methods: {
    login() {
      this.$auth.loginWith('local', {
        data: {
          username: this.username,
          password: this.password,
          code: this.code,
          sid: this.sid,
        },
      })
    },
  },
  // asyncData({ req }) {
  //   return {
  //     userAgent: req
  //       ? req.headers['user-agent']
  //       : typeof navigator !== 'undefined'
  //       ? navigator.userAgent
  //       : 'No user agent (generated)'
  //   }
  //   // ErrorHandle($axios, redirect)
  // }
  // asyncData: ({ req }) => {
  //   return {
  //     userAgent: req
  //       ? req.headers['user-agent']
  //       : typeof navigator !== 'undefined'
  //       ? navigator.userAgent
  //       : 'No user agent (generated)'
  //   }
  //   // ErrorHandle($axios, redirect)
  // }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
