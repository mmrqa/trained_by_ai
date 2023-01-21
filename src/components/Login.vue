<template>
    <div class="input-group mb-3 w-50">
      <input
        type="text"
        class="form-control"
        placeholder="Add your Emailaddresse"
        aria-label="Emailaddress"
        aria-describedby="btn-login"
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
</template>
<script>
export default {
  methods: {
    login() {},
  },
};
</script>
