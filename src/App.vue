<script >
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
    components :{
        AppHeader ,
        AppMain ,
    },
    data() {
        return {
            
            }
        }
}
</script>

<template>
    <body>
      <AppHeader  />
      <AppMain />
    </body>

</template>

<style lang="scss">
@use '../node_modules/bootstrap/scss/bootstrap.scss';
@use './styles/general.scss';

</style>
