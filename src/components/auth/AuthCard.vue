<template>
  <v-card
    width="400"
    class="mx-auto"
  >
    <auth-card-title :auth-type="authType" />

    <auth-social-container />

    <v-divider class="ma-8" />

    <sign-in-form v-if="authType==='sign in'" />
    <sign-up-form v-if="authType==='sign up'" />

    <sign-in-card-actions v-if="authType==='sign in'" />
    <sign-up-card-actions v-if="authType==='sign up'" />
  </v-card>
</template>

<script>
import AuthSocialContainer from '@/components/auth/AuthSocialContainer.vue';
import SignInForm from '@/components/auth/sign-in/SignInForm.vue';
import SignUpForm from '@/components/auth/sign-up/SignUpForm.vue';
import AuthCardTitle from '@/components/auth/AuthCardTitle.vue';
import SignInCardActions from '@/components/auth/sign-in/SignInCardActions.vue';
import SignUpCardActions from '@/components/auth/sign-up/SignUpCardActions.vue';

export default {
  name: 'AuthCard',

  components: {
    AuthCardTitle,
    AuthSocialContainer,
    SignInForm,
    SignUpForm,
    SignInCardActions,
    SignUpCardActions,
  },

  props: {
    authType: {
      type: String,
      required: true,
      validator(value) {
        return value === 'sign in' || value === 'sign up';
      },
    },
  },
};
</script>

<style scoped>

</style>
