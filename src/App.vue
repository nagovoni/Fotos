<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row>
          <v-col>
            <v-sheet min-height="70vh" rounded="lg">
              <v-carousel height="100%" show-arrows="hover" cycle hide-delimiter-background>
                <v-carousel-item v-for="(image, i) in roomData.property.propertyImages" :key="i">
                  <v-sheet height="700px">
                    <img :src="image.url" :alt="'Slide' + (i + 1)" />
                  </v-sheet>
                </v-carousel-item>
              </v-carousel>
            </v-sheet>
          </v-col>
          <v-col>
            <v-sheet min-height="70vh" rounded="lg">
              <v-carousel height="100%" show-arrows="hover">
                <v-carousel-item v-for="(image, i) in roomData.images" :key="i">
                  <v-sheet height="100%">
                    <img :src="image.url" :alt="'Slide' + (i + 1)" class="d-block w-100" />
                  </v-sheet>
                </v-carousel-item>
              </v-carousel>
              <v-card>
                <v-card-title>{{ roomData.displayName }}</v-card-title>
                <v-card-text>
                  <p><strong>Address:</strong> {{ roomData.property.address }}</p>
                  <p><strong>City:</strong> {{ roomData.property.city }}</p>
                  <p><strong>Room Description:</strong> <span v-html="roomData.roomDescription"></span></p>
                  <p><strong>Max People:</strong> {{ roomData.maxPeople }}</p>
                  <p><strong>Rack Rate:</strong> ${{ roomData.rackRate }}</p>
                  <p><strong>Cleaning Fee:</strong> ${{ roomData.cleaningFee }}</p>
                </v-card-text>
              </v-card>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>
<script setup>
import { ref } from 'vue'
import roomData from '../package.json'
const slides = ref(['First', 'Second', 'Third', 'Fourth', 'Fifth'])
</script>
