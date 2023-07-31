<template>
  <input
    type="email"
    class="form-control"
    placeholder="E-mail"
    :value="email"
    @input="update($event)"
    :class="{
      'is-valid': validateEmail(email),
      // email.length >= 4 && email.length > 0,
      'is-invalid': !validateEmail(email),
      // email.length < 4 && email.length > 0,
    }"
  />
</template>

<script>
import validateEmail from '@/validate-email';

export default {
  name: 'EmailInput',
  props: ['email'],
  methods: {
    update($event) {
      this.$emit(
        'update:email',
        $event.target.value
      );
    },
    validateEmail,
  },
  //   return {
  //     value: '',
  //   };
  // },
};
</script>
