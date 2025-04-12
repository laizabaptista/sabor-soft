<template>
    <v-app>
    <v-main class="main-container special-gothic-regular">
      <v-container class="py-10">
        <!-- Logo -->
        <v-img
        src="@/assets/saborsoft.png"
        max-width="250"
        class="mx-auto mb-8 animate__animated animate__fadeInDown"
        />
  
        <!-- Título -->
        <div class="text-center mb-10 animate__animated animate__fadeInUp">
        <h1 class="text-h3 font-weight-bold mb-2 text-pink-600 miniver">Cardápio de Bolos</h1>
        <p class="text-subtitle-1´-miniver">Feitos com carinho e ingredientes especiais</p>
        </div>
  
        <!-- Seção: Bolos Tradicionais -->
        <v-card class="pa-4 mb-6 rounded-xl shadow-lg" elevation="6">
        <h2 class="text-h5 font-weight-bold text-pink mb-4">Bolos Tradicionais</h2>
        <v-row dense>
          <v-col cols="12" sm="6" md="4" v-for="bolo in tradicionais" :key="bolo">
            <v-card class="pa-4 rounded-lg" elevation="3" color="#fffafa">
            <v-icon color="pink" size="20">mdi-cake</v-icon>
            <div class="text-body-1 font-weight-bold mt-2">{{ bolo.nome }}</div>
            <div class="text-body-2 font-weight-light text-pink">{{ bolo.preco }}</div>
            </v-card>
          </v-col>
        </v-row>
        </v-card>
  
        <!-- Seção: Bolos Especiais -->
        <v-card class="pa-4 mb-6 rounded-xl shadow-lg" elevation="6">
        <h2 class="text-h5 font-weight-bold text-pink mb-4">Bolos Especiais</h2>
        <v-row dense>
          <v-col cols="12" sm="6" md="4" v-for="bolo in especiais" :key="bolo">
            <v-card class="pa-4 rounded-lg" elevation="3" color="#fffafa">
            <v-icon color="pink" size="20">mdi-cake-variant</v-icon>
            <div class="text-body-1 font-weight-bold mt-2 ">{{ bolo.nome }}</div>
            <div class="text-body-2 font-weight-light text-pink">{{ bolo.preco }}</div>
            </v-card>
          </v-col>
        </v-row>
        </v-card>

        <!-- Seção: Vulcão -->
        <v-card class="pa-4 mb-6 rounded-xl shadow-lg" elevation="6">
        <h2 class="text-h5 font-weight-bold text-pink mb-4">Vulcão</h2>
        <p class="mb-4">Um clássico repaginado: massa fofinha com muito recheio, cobertura generosa por cima e o melhor — ao cortar,
             a cobertura escorre como lava em erupção! Um espetáculo visual e de sabor. Irresistivelmente delicioso!</p>
        <v-divider class="mb-4" />
        <v-row dense>
          <v-col cols="12" sm="6" md="4" v-for="bolo in vulcao" :key="vulcao">
            <v-card class="pa-4 rounded-lg" elevation="3" color="#fffafa">
            <v-icon color="pink" size="20">mdi-cake-variant</v-icon>
            <div class="text-body-1 font-weight-bold mt-2">{{ bolo.nome }}</div>
            <div class="text-body-2 font-weight-light text-pink">{{ bolo.preco }}</div>
            </v-card>
          </v-col>
        </v-row>
        </v-card>

        <!-- Seção: Bolos Salgados -->
        <v-card class="pa-4 mb-6 rounded-xl shadow-lg" elevation="6">
        <h2 class="text-h5 font-weight-bold text-pink mb-4">Bolos Salgados</h2>
        <v-row dense>
          <v-col cols="12" sm="6" md="4" v-for="bolo in salgados" :key="bolo.nome">
            <v-card class="pa-4 rounded-lg" elevation="3" color="#fffafa">
            <v-icon color="pink" size="20">mdi-food</v-icon>
            <div class="text-body-1 font-weight-bold mt-2">{{ bolo.nome }}</div>
            <div class="text-body-2 font-weight-light text-pink">{{ bolo.preco }}</div>
            </v-card>
          </v-col>
        </v-row>
        </v-card>
  
        <!-- Promoções -->
        <v-card class="pa-4 mb-6 rounded-xl shadow-lg" elevation="6">
        <h2 class="text-h6 font-weight-bold text-pink">Promoções</h2>
        <ul class="text-body-2 special-gothic-regular">
          <li>2 Bolos de R$25 por R$40</li>
          <li>2 Bolos de R$30 por R$50</li>
          <li>2 Bolos de R$20 por R$30</li>
          <li><strong>Bolos salgados não entram na promoção.</strong></li>
        </ul>
        </v-card>
  
        <!-- Contato e pagamento -->
        <v-card class="pa-4 mb-6 rounded-xl shadow-lg" elevation="6">
        <h2 class="text-h6 font-weight-bold text-pink">Formas de Pagamento</h2>
        <ul class="text-body-2 special-gothic-regular">
          <li>Pix</li>
          <li>Dinheiro</li>
          <li>Cartão de Crédito (acréscimo R$2 a R$3)</li>
        </ul>
        <p class="text-body-2 mt-2">Taxa de entrega: R$3</p>
        </v-card>
  
        <!-- Botões -->
        <div class="text-center">
        <v-btn color="pink" size="x-large" class="mb-3 shadow-lg px-6" @click="facaSeuPedido">
          <v-icon left>mdi-whatsapp</v-icon> Peça já pelo WhatsApp
        </v-btn>
        <p class="text-subtitle-2 mb-4">(21) 98402-8933</p>
        <v-btn variant="outlined" color="pink" href="https://instagram.com/saborsoftdc" target="_blank">
          <v-icon left>mdi-instagram</v-icon> Instagram
        </v-btn>
        </div>
      </v-container>
    </v-main>
    </v-app>
  </template>
  
  <script setup>
  import 'animate.css';

const tradicionais = [
    { nome: 'Bolo de Café com Cobertura Cremosa de Café', preco: 'R$20' },
    { nome: 'Bolo de Chocolate com Cobertura de Brigadeiro', preco: 'R$20' },
    { nome: 'Bolo de Cenoura com Cobertura de Chocolate', preco: 'R$20' },
    { nome: 'Bolo de Cenoura Frapê (Cenoura e Chocolate)', preco: 'R$20' },
    { nome: 'Bolo de Fubá com Pedaços de Goiabada', preco: 'R$20' },
    { nome: 'Bolo de Fubá com Erva Doce', preco: 'R$20' },
    { nome: 'Bolo de Fubá com Calda de Goiabada', preco: 'R$20' },
    { nome: 'Bolo de Limão com Cobertura de Mousse de Limão', preco: 'R$20' },
    { nome: 'Bolo de Laranja com Calda de Laranja', preco: 'R$20' },
]
  
const especiais = [
    { nome: 'Bolo de Coco com Cobertura de Beijinho', preco: 'R$25' },
    { nome: 'Bolo de Paçoca com Cobertura de Brigadeiro de Paçoca', preco: 'R$25' },
    { nome: 'Bolo de Churros com Cobertura de Doce de Leite', preco: 'R$25' },
    { nome: 'Bolo de Banana com Pedaços de Doce de Leite', preco: 'R$25' },
    { nome: 'Bolo de Maracujá com Cobertura de Mousse de Maracujá', preco: 'R$35' },
    { nome: 'Bolo de Milho com Goiabada', preco: 'R$25' },
    { nome: 'Bolo Formigueiro', preco: 'R$25' },
    { nome: 'Bolo de Nozes com Creme de Nozes', preco: 'R$30' },
    { nome: 'Bolo de Aipim (20cm)', preco: 'R$40' },
]
  
const vulcao = [
    { nome: 'Bolo de Cenoura com Brigadeiro Duplo', preco: 'R$40' },
    { nome: 'Bolo de Chocolate com Brigadeiro Duplo', preco: 'R$40' },
    { nome: 'Bolo de Nozes com Brigadeiro de Nozes', preco: 'R$50' },
    { nome: 'Bolo de Paçoca com Brigadeiro de Paçoca', preco: 'R$45' },
    { nome: 'Bolo de Café com Brigadeiro de Café', preco: 'R$45' },
]
  const salgados = [
    { nome: 'Bolo Presunto com Queijo Minas', preco: 'R$35' },
    { nome: 'Bolo de Calabresa com Mussarela', preco: 'R$35' },
    { nome: 'Bolo de Frango', preco: 'R$40'}
  ]
  
  const facaSeuPedido = () => {
    window.location.href = 'https://api.whatsapp.com/send?phone=5521984028933&text=Ol%C3%A1!%20Gostaria%20de%20fazer%20meu%20pedido!'
  }
  </script>
  
  <style scoped>
  ul {
    padding-left: 1rem;
    list-style-type: disc;
  }

  .main-container {
    background: url('@/assets/background.avif') repeat;
  }
  
  </style>
  