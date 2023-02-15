<script lang="ts" setup>
import { Navbar as SIGRHNavbar } from "@sigesp/sigrh-web";

defineProps<{
  modulo?: string
}>()
</script>

<template>
    <SIGRHNavbar v-if="modulo === 'sigrh'"/>
    <header v-else>
        Módulo não possui navbar
    </header>
</template>