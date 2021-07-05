<template>
  <div id="field" >
      <v-container>
        <section v-for="(fund, index) in defaultFunds" 
          :key="fund.name"
          class="mt-3"
        >
            <v-text-field
              v-model="newEntries[index].amount"
              :label="fund.label"
              :placeholder="fund.placeholder"
              :type="fund.type"
              outlined
              counter="80"
              background-color="grey darken-4"
              color="blue"
              :rules="rules"
            ></v-text-field>
        </section>
        
        <v-btn 
          outlined
          color="blue"
          @click="compute(), reports = !reports"
        
        >
          Hisobot
          <v-icon>
            mdi-arrow-down
          </v-icon>
        </v-btn>
        <Report 
          :allKredit="allKredit"
          :monthPay="monthPay"
          :totalProfit="totalProfit"
          :reports="reports"
          :newEntries="newEntries"
        />
        <Plan 
          :newEntries="newEntries" 
          :prise="prise"
          :spend="spend"
          :totalProfit="totalProfit"
          :monthPay="monthPay"
          :reports="reports"
           id="plan"/>
      </v-container>
      
  </div>
</template>

<script>
import Report from '@/components/report.vue'
import Plan from '@/components/plan.vue'
export default {
  components: {
    Plan,
    Report
  },
    data() {
        return {
          massage: 'hello',
          yangi:'',
          allKredit:'',
          spend:'',
          salary:'',
          prise: '',
          profit:'',
          totalProfit:'',
          monthPay: '',
          reports: false,
          rules: [val => (val || '').length > 0 || 'Ushbu qator to\'ldirilmadi!' ],
    defaultFunds: [
      {
        id: 100, 
        name: 'name',
        label:'Ism-familyangiz',
        placeholder: 'Korxona rahbarining ism-familyasi',
        type: 'text'
      },
      {
        id: 101,
        name: 'comName',
        label:'Korxona nomi',
        placeholder:'Korxona nomi',
        type: 'text'
      },
       {
        id: 102,
        name: 'goal',
        label:'Faoliyat maqsadi',
        placeholder:'Mazkur dastur faqatgina ishlab chiqarishga moslashgan',
        type: 'text'
      },
       {
        id: 103,
        name: 'product',
        label:'Qanday mahsulot ishlab chiqariladi',
        placeholder:'Ehtiyot qismlari, shinalar, textil mahsulotlari...',
        type: 'text'
      },
      {
        id: 104,
        name: 'totalValue',
        label:'Loyihaning umumiy qiymati ',
        placeholder:'So\'mda',
        type: 'number'
      },
      {
        id: 105,
        name: 'investor',
        label:'Shundan investor tomonidan qo\'shilgan qiymat ',
        placeholder:'So\'mda',
        type: 'number'
      },
      {
        id: 106,
        name: 'Bank',
        label:'Kredit ajratuvchi bank nomi ',
        placeholder:'Asia invest, Qishloq qurilish...',
        type: 'text'
      },
      {
        id: 107,
        name: 'kreditValue',
        label:'Kredit miqdori ',
        placeholder:'So\'mda',
        type: 'number'
      },
      {
        id: 108,
        name: 'persent',
        label:'Kredit foizi ',
        placeholder:'16, 18, 22, 24',
        type: 'number'
      },
      {
        id: 109,
        name: 'deadline',
        label:'Kredit qaytarish muddati ',
        placeholder:'Oylarda',
        type: 'number'
      },
       {
        id: 110,
        name: 'obekt',
        label:'Garovga qo\'yiluvchi o\'bekt nomi ',
        placeholder:'Oylarda',
        type: 'text'
      },
        {
        id: 111,
        name: 'items',
        label:'Olinuvchi jihozlar',
        placeholder: 'Barcha jihozlar',
        type: 'text'
      },
       {
        id: 112,
        name: 'costs',
        label:'Jihozlar uchun harajatlar',
        placeholder:'So\'mda',
        type: 'number'
      },
       {
        id: 113,
        name: 'prise',
        label:'Mahsulot tan narxi ',
        placeholder:'Bir dona mahsulot uchun ketgan harajat (So\'mda)',
        type: 'number'
      },
       {
        id: 114,
        name: 'mPrise',
        label:'Mahsulotning bozordagi narxi ',
        placeholder:'So\'mda',
        type: 'number'
      },
       {
        id: 115,
        name: 'production',
        label:'Kunlik ishlab chiqarish miqdori ',
        placeholder:'Dona yoki kilogramm',
        type: 'number'
      },
       {
        id: 116,
        name: 'sell',
        label:'Kunlik sotuv hajmi ',
        placeholder:'Dona yoki kilogramm',
        type: 'number'
      },
       {
        id: 117,
        name: 'worker',
        label:'Ishchilar soni ',
        placeholder:'',
        type: 'number'
      },
       {
        id: 118,
        name: 'salary',
        label:'Ishchilar maoshi ',
        placeholder:'O\'rtacha maosh miqdori',
        type: 'number'
      },
       {
        id: 119,
        name: 'iCost',
        label:'Ichki harajatlar ',
        placeholder:'Bu yerda ishchi kadrlarni o\'qitish va qayta tayyorlash uchun',
        type: 'number'
      },

    ],


        newEntries: [{}, {},{},{},{},{},{},{},{},{},{},{},{},{},{},{},{},{},{},{}]
     }
 },
    methods:{
      compute: function(){
        // kredit fizi
        this.allPersent = this.newEntries[7].amount / 100 * this.newEntries[8].amount
        // kredit foizi bilan
        this.allKredit = this.newEntries[7].amount * 1 + this.allPersent * 1
        // oylik to'lov
        this.monthPay = this.allKredit / this.newEntries[9].amount;
        // bir oyda ishlab chiqarish
        this.spend = (this.newEntries[13].amount * this.newEntries[15].amount) * 24;
        // bir oylik sotuv hajmi
        this.prise = (this.newEntries[14].amount * this.newEntries[16].amount) * 24;
        // ishcilar uchun oylik maosh
        this.salary = this.newEntries[18].amount * this.newEntries[17].amount
        // bir oylik daromad
        this.profit = this.prise - this.spend
        // bir oylik sof foyda
        this.totalProfit = this.profit - this.newEntries[19].amount - this.allKredit 
        console.log(this.allPersent, this.allKredit, parseInt(this.monthPay), this.spend, this.prise, this.profit, this.totalProfit );
      }
    }
}
</script>
<style scoped>
    #field{
        margin-top: 140px;
    }
</style>