<script setup lang="ts">
import { Navbar } from '@sigesp/components';

const items = [
  { label: "Cadastro", href: "#" },
  { label: "Lançamentos", href: "#" },
  { label: "Cálculo da Folha", href: "#" },
  { label: "Relatórios", href: "#" },
  { label: "Geração de Arquivos", href: "#" },
  { label: "Configurações", href: "#" },
  { label: "Sair", href: "/login" },
]

</script>

<template>
  <Navbar :items="items" />
</template>
