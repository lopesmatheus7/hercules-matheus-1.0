<template>
  <v-card>
    <v-navigation-drawer app v-model="drawer">
      <template v-slot:prepend>
        <v-list-item two-line>
          <v-list-item-avatar>
            <img src="https://upload.wikimedia.org/wikipedia/commons/8/8c/Cristiano_Ronaldo_2018.jpg" />
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>{{ user.username }}</v-list-item-title>
            <v-list-item-subtitle>Logado em</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item v-for="item in items" :key="item.title" :to="item.link" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  props: {
    drawer: {
      type: Boolean,
      default: null
    }
  },
  data: () => ({
    items: [
      { title: "Visão Geral", icon: "fas fa-laptop-house", link: "/" },
      { title: "Alunos", icon: "fas fa-user-plus", link: "/alunos" },
      {
        title: "Turmas",
        icon: "fas fa-chalkboard-teacher",
        link: "/turmas"
      },
      { title: "Cadastro de Alunos", icon: "fas fa-users", link: "/+alunos" },
      { title: "Cadastro de turmas", icon: "fas fa-trophy", link: "/+turmas" },
      { title: "Financeiro", icon: "fas fa-credit-card", link: "/Financeiro" },
      
      { title: "Configurações", icon: "fas fa-tools" },
      { title: "Relatórios", icon: "fas fa-plus-circle" }
    ]
  }),
  computed: {
    ...mapGetters(["user"])
  }
};
</script>

<style>
</style>