<template>
    <sidebar-menu :menu="menu" />
</template>
 
<script>
    import { SidebarMenu } from 'vue-sidebar-menu'
    import 'vue-sidebar-menu/dist/vue-sidebar-menu.css'

    export default {
        name: 'SideNavbar',
        data() {
            return {
                menu: [
                    {
                        header: true,
                        title: 'Main Navigation',
                        hiddenOnCollapse: true
                    },
                    {
                        href: '/',
                        title: 'Dashboard',
                        icon: 'fa fa-user'
                    },
                    {
                        href: '/charts',
                        title: 'Charts',
                        icon: 'fa fa-chart-area',
                        child: [
                            {
                                href: '/charts/sublink',
                                title: 'Sub Link'
                            }
                        ]
                    }
                ]
            }
        },
        components: {
            SidebarMenu
        }
    }
</script> 

<style scoped>
.v-sidebar-menu {
    display: flex;
    position: sticky;
    float: left;
    /* width: 200px; */
    /* margin-top: 60px; */
    height: calc(100vh - 120px);
}
</style>