<template>
  <div class="input-group mb-3 w-50">
    <input
      type="text"
      class="form-control"
      placeholder="Add your Emailaddresse"
      aria-label="Emailaddress"
      aria-describedby="btn-login"
      v-model="useremail"
    />
    <button
      @click="login"
      class="btn btn-outline-success"
      type="button"
      id="btn-login"
    >
      Login
    </button>
  </div>
  <pre class="text-muted">{{ statusLoginText }}</pre>
</template>
<script>
export default {
  data() {
    return {
      useremail: "",
      statusLoginText: "",
    };
  },
  methods: {
    async login() {
      let p = new Passwordless.Client({
        apiKey: "mmrqa:public:0b1456c994ef46079ab72c1ed5c1a08b",
      });

      let alias = this.useremail;

      // yUf6_wWdDh02ItIvnCKT_02ItIvn...
      let token = await p.signinWithAlias(alias);

      const param = { SignInToken: token };
      const signInUserResult = await Parse.Cloud.run("signinUser", param);
      const verifiedUser = JSON.parse(signInUserResult);
      console.log(verifiedUser);
      console.log(verifiedUser.success);

      if (verifiedUser.success === true) {
        this.statusLoginText = "You are In!";
      }
    },
  },
};
</script>
