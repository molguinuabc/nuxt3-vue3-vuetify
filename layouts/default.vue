<template>
  <v-app id="inspire">
    <v-app-bar >
      <v-container class="fill-height ">
        <v-avatar
          class="me-10 ms-4"
          color="grey-darken-1"
          size="32"
        ></v-avatar>
        
        <div v-if="logged">
          <v-btn 
            v-for="link in menu.links"
            :key="link"
            variant="text"
            @click="logged=!logged"
          >
            {{ link }}
          </v-btn>
        </div>
        <v-spacer></v-spacer>
        <div v-if="!logged" class="d-flex justify-space-between" >
          <v-btn 
            v-for="link in menu.login"
            :key="link"
            variant="text"
            @click="logged=!logged"           
          >
            {{ link }}
        </v-btn>
        </div>

      </v-container>
    </v-app-bar>

    <v-main class="bg-grey-lighten-3">
      <v-container>
        <v-row>
          <v-col cols="2">
            <v-sheet rounded="lg">
              <v-list rounded="lg">
                <v-list-item
                  link
                  color="grey-lighten-4"
                >
                  <v-list-item-title>
                    <NuxtLink to="/"> Home </NuxtLink>
                  </v-list-item-title>
                </v-list-item>
                <v-list-item
                  link
                  color="grey-lighten-4"
                >
                  <v-list-item-title>
                    <NuxtLink to="/about"> About </NuxtLink>
                  </v-list-item-title>
                </v-list-item>
                
                <v-divider class="my-2"></v-divider>
                
                <v-list-item
                  v-for="n in 5"
                  :key="n"
                  link
                >
                  <v-list-item-title>
                    List Item {{ n }}
                  </v-list-item-title>
                </v-list-item>

              </v-list>
            </v-sheet>
          </v-col>

          <v-col>
            <v-sheet
              min-height="70vh"
              rounded="lg"
            >
              <NuxtPage />
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue';
import { useLogged } from '~~/composables/states';
    const menu = ref({
      links: [
        'Dashboard',
        'Messages',
        'Profile',
        'Updates',
      ],
      login: [
        'Login'
      ]
    });
    const logged = useLogged();
</script>

<style >

.page-enter-active,
.page-leave-active {
  transition: all 0.4s;
}
.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: blur(1rem);
}

.rotate-enter-active,
.rotate-leave-active {
  transition: all 0.4s;
}
.rotate-enter-from,
.rotate-leave-to {
  opacity: 0;
  transform: rotate3d(1, 1, 1, 15deg);
}
</style>