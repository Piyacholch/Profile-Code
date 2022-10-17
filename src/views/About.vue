<template>
  
    <h1>update</h1>
    <form >
        <h2>Piease verify your email.</h2>
        <button type="submit" @click="verification()">verification</button>
    </form>
</template>
<script >
import {getAuth,sendEmailVerification } from "firebase/auth";
export default {
  data() {
    return {
    };
  },
  methods: {

    async verification() {
      const auth = getAuth();
      sendEmailVerification(auth.currentUser).then(() => {
        // Email verification sent!
        // ...
      });
    },
  },

  created() {
    this.verification();
  },
};
</script >
