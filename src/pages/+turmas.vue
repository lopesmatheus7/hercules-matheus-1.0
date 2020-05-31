<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="600px">
      <template v-slot:activator="{ on }">
        <v-btn color="primary" dark v-on="on">+ Aluno</v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="headline">Cadastro de aluno</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12">
                <v-text-field label="Primeiro nome" required></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="Sobrenome" required></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  label="Nome do Responsável 1*" hint="examplo João"                    
                ></v-text-field>
              </v-col> 
              <v-col cols="12">
                <v-text-field
                  label="Nome do Responsavel 2*" hint="exemplo: João"
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="Email*" required></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="Senha*" hint= "Mínimo 4 caractéres" type="password" required></v-text-field>
              </v-col>
              <v-col cols="12" sm="6">
                <v-text-field label="Nascimento" required></v-text-field>
              </v-col>
              <v-col cols="12" sm="6">
                <v-select
                  :items="items"
                  label="Turma"
                  :rules="[v => !!v || 'Item is required']"
                  required
                ></v-select>
              </v-col>
            </v-row>
          </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="dialog = false">Fechar</v-btn>
          <v-btn color="blue darken-1" text @click="dialog = false">Salvar</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>


<script>
  export default {
    data: () => ({
      dialog: false,

      select: null,
      items: [
        'Terça e quinta',
        'Segunda e Quarta',
        'Quarta e Sexta',
        'Sabado'
      ],
      checkbox: false 
    }),
  }
    
</script>


