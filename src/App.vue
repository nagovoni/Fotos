<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row>
          <v-col cols="12">
            <v-sheet>
              <v-card-title>{{ roomData.property.name }}</v-card-title>
              <v-carousel show-arrows="hover" cycle hide-delimiter-background>
                <v-carousel-item v-for="(image, i) in roomData.property.propertyImages" :key="i">
                  <v-sheet>
                    <img :src="image.url" :alt="'Slide' + (i + 1)" width="1200px" height="500px" />
                  </v-sheet>
                </v-carousel-item>
              </v-carousel>
            </v-sheet>
          </v-col>
          <v-col cols="12">
            <v-card>
              <v-card-title>{{ roomData.displayName }}</v-card-title>
                <v-container fluid>
                  <v-row>
                    <v-col v-for="(image, i) in roomData.images" :key="i" cols="3" xs="6" sm="4">
                      <v-img :src="image.url" :alt="`Imagem do Quarto ${i + 1}`" class="image-container" />
                    </v-col>
                  </v-row>
                </v-container>
              <v-card-text>
                <p><strong>Address:</strong> {{ roomData.property.address }}</p>
                <p><strong>City:</strong> {{ roomData.property.city }}</p>
                <p><strong>Room Description:</strong> <span v-html="roomData.roomDescription"></span></p>
                <p><strong>Max People:</strong> {{ roomData.maxPeople }}</p>
                <p><strong>Rack Rate:</strong> ${{ roomData.rackRate }}</p>
                <p><strong>Cleaning Fee:</strong> ${{ roomData.cleaningFee }}</p>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>
<script setup>

import roomData from '../src/pages/roomData.json'

</script>
