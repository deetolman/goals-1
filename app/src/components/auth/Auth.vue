<template>
  <section>
    <div v-if="method === 'signin'">
      <h2>Sign In</h2>
      <p>
        <button @click="method = 'signup'">Sign Up</button>
      </p>
       <form @submit.prevent="onSignIn(profile)">
        <label>
          Username:
          <input v-model="profile.username" required>
        </label>
        <label>
          Password:
          <input type="password" v-model="profile.password" required>
        </label>
        <label>
          <button>Sign In</button>
        </label>
      </form>
    </div>
     <div v-else>
      <h2>Sign Up</h2>
      
      <p>
        Already have an account?
        <button @click="method = 'signin'">Sign In</button>
      </p>
       <form @submit.prevent="onSignUp(profile)">
        <label>
          Username:
          <input v-model="profile.username" required>
        </label>
        <label>
          Password:
          <input type="password" v-model="profile.password" required>
        </label>
        <label>
          <button>Sign Up</button>
        </label>
      </form>
    </div>
   </section>
</template>
<script>
export default {
  props: {
    onSignIn: Function,
    onSignUp: Function
  },
  data() {
    return {
      method: 'signin',
      profile: {
        username: '',
        password: ''
      }
    };
  }
};
</script>
 <style lang="postcss" scoped>
 label {
  display: block;
  padding: 10px 0;
}
</style>
