<template>
  <q-layout view="lHh Lpr lFf">
    <q-header >
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

      </q-toolbar>
      <div class="q-px-lg q-pt-xl q-mb-md">
        <div class="text-h3">Todo</div> 
        <div class="text-subttittle1"> Monday 4 November</div>
      </div>
      <q-img
         src="../statics/bg.jpg"
        class="header-image absolute-top">
      </q-img>
    
    </q-header>

     <q-drawer
        v-model="leftDrawerOpen"
        show-if-above
        :width="250"
        :breakpoint="600"
      >
        <q-scroll-area style="height: calc(100% - 185px); margin-top: 185px; border-right: 1px solid #ddd">
          <q-list padding>
            <q-item 
            to="/"
            clickable
            v-ripple
            exact>
              <q-item-section avatar>
                <q-icon name="list" />
              </q-item-section>

              <q-item-section>
                Todo
              </q-item-section>
            </q-item>

             <q-item
                to="/help"
                 clickable
                 v-ripple
                 exact>
              <q-item-section avatar>
                <q-icon name="help" />
              </q-item-section>

              <q-item-section>
                help
              </q-item-section>
            </q-item>          
          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="../statics/bg.jpg" style="height: 185px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="q-mb-sm">
              <img src="https://cdn.quasar.dev/img/boy-avatar.png">
            </q-avatar>
            <div class="text-weight-bold">Sharifah Hasyimah</div>
            <div>@syifaima</div>
          </div>
        </q-img>
      </q-drawer>

    <q-page-container>
      <keep-alive>
         <router-view />
      </keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>
import { date } from 'quasar'

export default {
  name: 'MyLayout',
  data () {
    return {
      leftDrawerOpen: false
    }
  },
  computed: {
    todaysDate() {
      let timeStamp = Date.now()
      let formattedString = date.formatDate(timeStamp, 'YYYY-MM-DDTHH:mm:ss.SSSZ')
    }
  }
}



</script>

<style lang="scss">
     .header-image{
       height: 100%;
       z-index: -1;
       opacity: 0.2;
     }
</style>