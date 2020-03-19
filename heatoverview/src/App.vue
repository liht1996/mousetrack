<template>
  <div id="app">
    <AccountNavbar/>
    <b-container>
      <b-row >
        <b-col style="max-width: 200px; min-width: 100px" md="auto">
          <SideNavbar class='vsm_white-theme' />
        </b-col>
        <b-col style="max-width: 1920px; margin-left:100px; overflow: scroll" md="auto">
          <Heatmap id="heatmap"/>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Heatmap from './components/Heatmap'
import AccountNavbar from './components/AccountNavbar'
import SideNavbar from './components/SideNavbar'
import { BContainer, BRow, BCol} from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {
  name: 'App',
  components: {
    AccountNavbar,
    Heatmap,
    SideNavbar,
    BContainer,
    BRow,
    BCol

  },
  mounted(){

  },
  method:{
    
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
#heatmap {
  /* margin-top: 60px; */
}
@media (min-width: 1200px){
  .container{
    max-width:1920px;
  }  
}

</style>
