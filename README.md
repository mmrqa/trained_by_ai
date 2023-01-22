# trained_by_ai
You're one of the "home workout" sportstyp? Whats more anoying then to create a workout routine for every trainingday? 
The solution is to use AI. The trainedbyAI-App uses ChatGPT to create workout routines on weekly basis. Each one is created under the behalf of each users individual inputs. 

The second major part of the app takes care of the authentification for users. The app will make use of passkeys as passwords will be substituted in the future. More information about the underlaying standards check: <a href="https://fidoalliance.org/passkeys/">https://fidoalliance.org/passkeys/</a>     

### Authentification using Passkeys with help of Passwordless.dev

#### Registration Flow

The registration of a new User will be made after the following flow:

1. New User enters his emailaddress as username
2. Frontend will deliver the emailaddress to backend
    2.1 Backend check if user exists and requesting browser/operating system is already used for passkey exchange with passwordless.dev
    2.2 If the User already has exchanged a key with passwordless.dev for the requesting browser, than the User will be promted to login
    2.3 If the User has not exchanged a key with passwordless.dev for the requesting browser yet, than a subuser will be created and a new key exchanged with passwordless.dev
3. Backend provides the generated token to frontend where the Api will take it to link the created User with the following created key
4. User will be promted by passwordless.dev to authentificate via Faceid/Fingerprint/Pin etc. 
5. User is now verified for the app
6. User needs to verify emailaddress after


### Create workout plan with ChatGPT 


This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
