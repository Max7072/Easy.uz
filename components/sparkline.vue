<template>
  <v-card
    class="mx-auto text-center"
    dark
    max-width="800"
  >
    <v-card-text>
      <v-sheet dark>
        <v-sparkline
          :value="value"
          color="rgba(255, 255, 255, .7)"
          height="100"
          padding="24"
          stroke-linecap="round"
          smooth
          class="blue--text"
        >
          <template v-slot:label="item">
            ${{ item.value }}
          </template>
        </v-sparkline>
      </v-sheet>
    </v-card-text>

    <v-card-text>
      <div class="text-h4 font-weight-thin">
        Sales Last 24h
      </div>
    </v-card-text>
    <v-card-text>
      <div class="ma-5">
        Ushbu bo'limda siz biznes reja tuzishingiz va bir qancha rejalarni sinab ko'rishingiz mumkin. <br>
        Sizga bir nechta savollar beriladi va biznes reja avtomatik tarzda tuzib boriladi.
      </div>
    </v-card-text>

    <v-divider></v-divider>

    <v-card-actions class="justify-center">
      <v-btn
        block
        outlined
        disabled
        color="blue"
      >
        Biznes reja
         <v-icon >
          mdi-arrow-down
        </v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template> 
<script>
  export default {
    data: () => ({
      value: [
        423,
        446,
        675,
        510,
        590,
        610,
        760,
      ],
    }),
  }
</script>