<template>
  <h1 class="heading-1">Inputs</h1>

  <form @submit.prevent="submitForm">
    <Input 
      label="Your name"
      name="name"
      placeholder="Input Name"
      v-model:value="v.namefild.$model"
      :error="v.namefild.$errors"
    />
    <Input 
      label="Your email"
      name="email"
      placeholder="Input Email"
      v-model:value="v.emailfild.$model"
      :error="v.emailfild.$errors"
    />
    <Input 
      label="Your Number"
      name="number"
      placeholder="Input Number"
      v-model:value="v.luckyField.$model"
      :error="v.luckyField.$errors"
    />
    <Input 
      label="Your Pass"
      name="password"
      placeholder="Input Your password"
      v-model:value="passwordField"
      type="password"
    />
    <Input 
      label="Confirm Pass"
      name="confirmPassword"
      placeholder="Confirm your password"
      v-model:value="v.confirmPasswordField.$model"
      :error="v.confirmPasswordField.$errors"
      type="password"
    />
    <Input 
      label="Word"
      name="Word"
      placeholder="Input Word"
      v-model:value="v.frontendField.$model"
      :error="v.frontendField.$errors"
    />
    <Button label="submit" color="primary"></Button>
  </form>
</template>

<script setup>
import Input from '@/components/Input.vue'
import {ref, computed} from 'vue'
import Button from '@/components/Button.vue'
import userVuelidate, { useVuelidate } from '@vuelidate/core'
import {helpers, minLength, maxLength, numeric, email, sameAs} from '@vuelidate/validators'

const namefild = ref('')
const emailfild = ref('')
const luckyField = ref('')
const passwordField = ref('')
const confirmPasswordField = ref('')
const frontendField = ref('')

const mustBeFrontend = (value) => value.includes('frontend')

const submitForm = () => {
  v.value.$touch()
  if(v.value.$error) return
  alert('Form Submited')
}

const rules = computed(() => ({
  namefild: {
    minLength: helpers.withMessage('Минимальная длина 3 символа', minLength(3))
  },
  emailfild: {
    email: helpers.withMessage('Вы ввели неверный email', email)
  },
  luckyField: {
    maxLength: helpers.withMessage('Максимальная длина 2 символа', maxLength(2)),
    numeric: helpers.withMessage('Вы можете ввести только цифры', numeric)
  },
  confirmPasswordField: {
    sameAsPassword: helpers.withMessage('Пароли не совпадаят', sameAs(passwordField.value))
  },
  frontendField: {
    frontendField: helpers.withMessage('Строка должна содержать слово frontend', mustBeFrontend)
  }
}))

const v = useVuelidate(rules, {namefild, emailfild, luckyField, confirmPasswordField, frontendField})
</script>
