<script>
import NavItem from './components/NavItem/NavItem.vue'
import NavView from './views/NavView.vue'
import HeaderView from './views/HeaderView.vue';
import HeaderItem from './components/HeaderItem/HeaderItem.vue';
import HeaderButtons from './components/HeaderButtons/HeaderButtons.vue';
import HomeView from './views/HomeView.vue';
export default {
  components: { NavView, NavItem, HeaderView, HeaderItem, HeaderButtons, HomeView },
  name: 'App',
}
</script>

<template>
  <div class="absolute z-10 w-full">
    <nav-view>
      <nav-item href="/contactez-nous" isActive>Contactez-nous</nav-item>
      <nav-item href="/espace-presse">Espace Presse</nav-item>
      <nav-item href="/devenir-franchise">Devenir Franchisé</nav-item>
    </nav-view>
    <header-view>
      <template v-slot:menu>
        <header-item>Crédit immobilier</header-item>
        <header-item>Assurance de prêt</header-item>
        <header-item>Actualités</header-item>
        <header-item>Agences</header-item>
      </template>
      <template v-slot:buttons>
        <header-buttons background="bg-[#F59758]">Credit<br>Application</header-buttons>
        <header-buttons background="bg-gradient-to-b from-[#129D5B] to-[#198B55]">Comparer<br>Assurance</header-buttons>
        <header-buttons background="bg-gradient-to-b from-[#39D2DE] to-[#36BEC9]">Loan<br>Simulators</header-buttons>
      </template>
    </header-view>
  </div>
  <div class="relative h-screen bg-[#0480BB] overflow-hidden">
    <div class="pt-[148px] flex md:block items-center w-full h-full bg-cover md:bg-contain bg-right bg-no-repeat bgVectors">
      <home-view></home-view>
    </div>
  </div>
</template>

<style scoped>
.bgVectors{
  background-image: url('./media/bgVectors.png');
}
</style>
