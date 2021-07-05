<template>
  <div id="cont" v-if="reports">
      <v-card id="card">
        <div class="d-flex justify-space-between" id="progress">
            <v-progress-circular
              :rotate="360"
              :size="50"
              :width="7"
              :value="value"
              color="blue"
            >
              <v-icon color="indigo lighten-3">
                mdi-text-box-check
              </v-icon>
            </v-progress-circular>
            <v-progress-circular
              :rotate="360"
              :size="50"
              :width="7"
              :value="value"
              color="red"
            >
              <v-icon>
                mdi-progress-check
              </v-icon>
          </v-progress-circular>
          <v-progress-circular
              :rotate="360"
              :size="50"
              :width="7"
              :value="value"
              color="purple lighten-3"
          >
            <v-icon color="purple lighten-3">
              mdi-currency-usd
            </v-icon>
          </v-progress-circular>
        </div>
        <v-divider ></v-divider>
          <v-card-title class="justify-center">
             <h3>  Umumiy ma'lumotlar:  </h3> 
          </v-card-title>
          <v-divider ></v-divider>
          <v-card-text>
              Kredit umumiy qiymati: {{allKredit}}
          </v-card-text>
          <v-divider ></v-divider>
          <v-card-text>
              Kredit qaytarsh oyiga: {{monthPay}}
          </v-card-text>
          <v-divider ></v-divider>
          <v-card-text>
            Jihozlar uchun harajatlar: {{newEntries[12].amount}}
          </v-card-text>
          <v-card-text>
            Bir oylik sof foyda: {{totalProfit}}
          </v-card-text>
         
    </v-card>
  </div>
</template>

<script>
export default {
    data () {
      return {
        interval: {},
        value: 0,
      }
    },
    beforeDestroy () {
      clearInterval(this.interval)
    },
    mounted () {
      this.interval = setInterval(() => {
        if (this.value === 100) {
          return (this.value = 0)
        }
        this.value += 10
      }, 1000)
    },
    props:['allKredit', 'monthPay', 'totalProfit', 'reports', 'salary', 'newEntries']
}
</script>

<style scoped>
    #cont{
        width: 100%;
        margin-top: 20px;
    }
    #card{
        width: 40%;
        margin: auto;
    }
    #progress{
      padding: 20px;
    }
</style>