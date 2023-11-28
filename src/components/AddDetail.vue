<script setup>
import { ref, defineEmits } from 'vue'

const emit = defineEmits(['addDetail'])

const person = ref({idNum:'', name: '', email: '', phone: '', assignee:'' })

const submitForm = () => {
  if (person.value.name === '')
    return 'You must enter a first name.'
  emit('addDetail',person.value)
  person.value = { idNum:'', name: '', email: '', phone: '', assignee:'' }
}
</script>

<template>
  <v-sheet width="300" class="mx-auto">
    <v-form @submit.prevent=submitForm>
      <v-text-field
        v-model="person.name"
        type="text"
        label="Full name"
        :rules="rules"
      ></v-text-field>
      <v-text-field
        v-model="person.email"
        type="email"
        label="Email"
      ></v-text-field>
      <v-text-field
        v-model="person.phone"
        type="text"
        label="Phone number"
      ></v-text-field>
      <v-text-field
        v-model="person.idNum"
        type="text"
        label="ID number"
      ></v-text-field>
      <v-select
        v-model="person.assignee"
        :items="['A','B']"
        label="person.assignee"
      ></v-select>
      <v-btn type="submit" block class="mt-2">Submit</v-btn>
    </v-form>
  </v-sheet>
</template>
