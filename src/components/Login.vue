<template>
    <div class="d-flex flex-column align-items-center justify-content-center h-100">
        <div class="input-group mb-3 w-25">
            <input type="text" class="form-control" placeholder="Add your Emailaddresse" aria-label="Emailaddress"
                aria-describedby="btn-register" />
            <button @click="register" class="btn btn-outline-secondary" type="button" id="btn-register">
                Register
            </button>

        </div>
        <div class="card w-25">
            <div class="card-body">
                <h3>And where can I add my password?</h3>
                <small>Since the release of so called 'Passkeys' it is no longer needed to generate your unique password.
                    Your operation system will use their authentification methods to generate a key which will be used to identify yourself.
                    Lern more about Passkeys from here: <a href="https://fidoalliance.org/passkeys/">https://fidoalliance.org/passkeys/</a></small> 
            </div>
        </div>
    </div>
</template>
<script>
export default {
    methods: {
        register() { },
    },
};
</script>
