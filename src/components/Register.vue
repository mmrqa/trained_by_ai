<template>

    <div class="input-group mb-3 w-50">
        <input type="text" class="form-control" v-model="useremail" placeholder="Add your Emailaddresse"
            aria-label="Emailaddress" aria-describedby="btn-register" />
        <button @click="register" class="btn btn-outline-secondary" type="button" id="btn-register">
            Register
        </button>
    </div>
    <div class="card w-50">
        <div class="card-body">
            <h3>And where can I add my password?</h3>
            <small>Since the release of so called 'Passkeys' it is no longer needed to
                generate your unique password. Your operation system will use their
                authentification methods to generate a key which will be used to
                identify yourself. Lern more about Passkeys from here:
                <a href="https://fidoalliance.org/passkeys/">https://fidoalliance.org/passkeys/</a></small>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            useremail: ''
        }
    },
    methods: {
        async register() {
            var p = new Passwordless.Client({
                apiKey: "mmrqa:public:0b1456c994ef46079ab72c1ed5c1a08b"
            });

            const param = { email: this.useremail }
            const token = await Parse.Cloud.run('registeruser', param);
            console.log(token);

            try {
                await p.register(token);
                console.log("registrierung erfolgreich");
            } catch (e) {
                // error    
            }

        },
    }
}
</script>
