<template>
  <div class="login">
    <div class="fill-height" fluid>
      <div
        align="center"
        justify="center"
      >
        <div cols="12" sm="8" md="6" lg="4">
          ChatApp
        </div>
      </div>
      <div align="center" justify="center">
        <div cols="12" sm="8" md="6" lg="4">
          <div class="elevation-12">
            <div color="primary" dark flat>
              <div>Login form</div>
              <div></div>
            </div>
            <div>
              <div>
                <!-- <input
                  label="UserId"
                  name="login"
                  prepend-icon="mdi-account"
                  type="text"
                  v-model="userId"
                /> -->
                <input
                  name="login"
                  type="text"
                  v-model="userId"
                />

                <!-- <input
                  id="password"
                  label="Password"
                  name="password"
                  prepend-icon="mdi-lock"
                  :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  :type="showPassword ? 'text' : 'password'"
                  @click:append="showPassword = !showPassword"
                  @keyup.enter="login"
                  v-model="password"
                /> -->
                <input
                  id="password"
                  name="password"
                  v-model="password"
                />
              </div>
            </div>
            <div>
              <div align="center" justify="space-around">
                <button color="#B2EBF2" @click="login">Login</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Login",
  components: {},
  data: () => ({
    showPassword: false,
    userId: "",
    password: "",
  }),
  methods: {
    login() {
      // 入力されたログイン情報が正しいか確認
      this.$store.dispatch("login", {
        userId: this.userId,
        password: this.password,
      });
    },
  },
};
</script>