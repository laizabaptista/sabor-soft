<template>
  <v-app>
    <v-main class="d-flex align-center justify-center" style="min-height: 100vh; background: #fff0f5;">
      <v-container class="text-center">
        <!-- Logo no centro -->
        <v-img
          src="@/assets/saborsoft.png"
          max-width="300"
          class="mx-auto mb-6"
          alt="Logo da Empresa"
        />

        <!-- Botões -->
        <div class="d-flex flex-column align-center">
            <v-btn
            color="pink"
            class="mb-4"
            size="large"
            variant="flat"
            @click="() => $router.push('/cardapio')"
          >
            Cardápio 
          </v-btn>
          <v-btn
            color="red"
            class="mb-4"
            size="large"
            variant="flat"
            @click="facaSeuPedido"
          >
            Faça seu pedido
          </v-btn>

          <v-btn
            color="pink"
            size="large"
            variant="outlined"
            href="https://instagram.com/saborsoftdc"
            target="_blank"
          >
            Instagram
          </v-btn>
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
const facaSeuPedido = () => {
  // Aqui você pode redirecionar ou abrir um modal, por exemplo:
  window.location.href = "https://api.whatsapp.com/send?phone=5521984028933&text=Ol%C3%A1!%20Gostaria%20de%20fazer%20meu%20pedido!"
}
</script>

<style scoped>
/* Fundo suave rosa-claro combinando com a paleta */
</style>
