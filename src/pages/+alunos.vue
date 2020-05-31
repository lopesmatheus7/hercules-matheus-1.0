<template>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="name"
      :counter="10"
      :rules="nameRules"
      label="Nome Completo"
      required
    ></v-text-field>

<v-text-field
      v-model="date"
      :counter="10"
      :rules="dateRules"
      label="Data de nascimento"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>

<v-text-field
      v-model="nameresponsavel1"
      :rules="responsavel1Rules"
      label="Nome do responsável 1"
      required
    ></v-text-field>

    <v-text-field
      v-model="nameresponsavel2"
      :rules="responsavel2Rules"
      label="Nome do responsável 2"
      required
    ></v-text-field>

    <v-text-field
      v-model="Address"
      :rules="AddressRules"
      label="Endereço"
      required
    ></v-text-field>

    <v-text-field
      v-model="phone"
      :rules="phoneRules"
      label="Celular"
      required
    ></v-text-field>

    <v-select
      v-model="select"
      :items="items"
      :rules="[v => !!v || 'Item is required']"
      label="Selecione a turma"
      required
    ></v-select>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Você aceita?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      @click="enviar"
    >
      Enviar
    </v-btn>

    <v-btn
      color="error"
      @click="apagar"
    >
      Reset Form
    </v-btn>
    >
  </v-form>
</template>

<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 60) || 'Name must be less than 10 characters'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ],
      select: null,
      items: [
        'Terça e quinta',
        'Segunda e Quarta',
        'Quarta e Sexta',
        'Sabado'
      ],
      checkbox: false
    }),

    methods: {
      validate () {
        if (this.$refs.form.validate()) {
          this.snackbar = true
        }
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      }
    }
  }
</script>