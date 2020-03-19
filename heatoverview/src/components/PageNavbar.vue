<template>
<div>
  <b-navbar toggleable="lg" type="dark" variant="secondary" >
    <b-navbar-brand >
        {{currentLink}}
    </b-navbar-brand>
  </b-navbar>
</div>
</template>

<script>
import { BNavbarBrand, BNavbar} from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default{
    name: 'PageOverview',
    props:['currentLink'],
    data(){
        return {
        }
    },
    components: {
      BNavbar,
      BNavbarBrand,
    },
    beforeMount(){

    },
    methods:{

    }
}

</script>