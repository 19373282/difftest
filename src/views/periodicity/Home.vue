<template>
    <v-app class="vueWrap" dark>
        <!-- Navigation menu/header -->
        <Navigation @showTable="isShowTable"/>
        <!-- Periodic Table -->
        <div class="tableWrap">
            <PeriodicTable/>
        </div>
        <!-- Footer -->
        <div style="clear:both;">
            <DownTable v-show="showTable"/>
        </div>
    </v-app>
</template>

<script>
import PeriodicTable from '@/components/home/PeriodicTable'
import Navigation from '@/components/home/Navigation'
import DownTable from '@/components/home/Table'

export default {
  name: 'Home',
  data () {
    return {
      showTable: false
    }
  },
  components: {
    Navigation,
    PeriodicTable,
    DownTable
  },
  methods: {
    isShowTable (table) {
      this.showTable = table
    }
  }
}
</script>

<style lang="scss">
body {
    margin: 0;
}
.vueWrap{background: #1a1d27 !important;}
.application.theme--dark {
    background: rgb(26, 31, 44) !important;
}
.application .theme--dark.v-navigation-drawer .v-divider,
.application
    .theme--dark.v-navigation-drawer:not(.v-navigation-drawer--floating)
    .v-navigation-drawer__border,
.theme--dark .v-navigation-drawer .v-divider,
.theme--dark
    .v-navigation-drawer:not(.v-navigation-drawer--floating)
    .v-navigation-drawer__border {
    background: none;
}
.tableWrap {
    width: 88.1%;
    margin-left: auto;
    margin-right: auto;
    clear: both;
    padding-bottom: 4vw;
}
.footerWrap {
    width: 100%;
}
@media only screen and (max-width: 600px) {
    .tableWrap {
        width: 100%;
        overflow: scroll;
        clear: both;
        padding-bottom: 4vw;
    }
}
</style>
