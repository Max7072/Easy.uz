<template>
  <v-container v-if="reports">
    <div  id="content">
      <v-card  light>
        <div id="container">
          <v-card-title class="ma-3 ">
            1.Kirish
          </v-card-title>
          <v-card-text>
            "{{newEntries[1].amount}} " xususiy korxonasi   {{newEntries[3].amount}} ishlab chiqarishni o'z oldiga maqsad qilib qo'ygan 
            bo'lib, natijada ushbu xizmat turiga bo'lgan talablarni nisbatan qondirishga qaratilgan. Loyihaning umumiy qiymati {{newEntries[4].amount}}
             so'mni tashkil qiladi. Mazkur faoliyatni amalga oshirish uchun ivestor tomonidan {{newEntries[5].amount}} so'm va 
             ishlab chiqarish uskunasi hamda xom ashyolar sotib olish uchun 
            "{{newEntries[6].amount}}" bank mablag'i xisobidan {{newEntries[7].amount}} so'm miqdorda {{newEntries[9].amount}} oy muddatga 
            {{newEntries[8].amount}}% ustamasi bilan kredit mablag'i zarur.
          </v-card-text>
          <v-card-title>
            2.Xizmat ko'rsatish rejasi
          </v-card-title>
          <v-card-text>
            Xizmat ko'rsatish rejasi va ko'rsatiladigan xizmatlar turi kredit xisobidan, sotib olinadigan asbob-uskunalarning 
            ishlab chiqarish 
            quvvati va texnik imkoniyatlaridan kelib chiqqan xolda tuzildi.
            Ko'rsatiladigan xizmatlar xajmi 1 oyda ya'ni 24 ish kunida loyiha bo'yicha to'liq quvvatda ishlaganda 
            {{newEntries[14].amount * 24}}
            dona {{newEntries[3].amount}}
            ishlab chiqariladi. <br>
            Xizmat ko'rsatish rejasini tuzishda ishlab chiqarishini tashkillashtirish jarayoni ham e'tiborga olindi.

          </v-card-text>
          <v-card-title>
            3.Ishlab chiqarish rejasi
          </v-card-title>
          <v-card-text>
            Korxonada bir smenalik ish rejimi, xaftada 6 ish kunlik tashkillashtirish rejalashtirilgan. 
            Yil 256 ish kunidan iborat. Bir kunda jami {{newEntries[15].amount}} dona 1 oyda {{newEntries[15].amount * 24}} 
            dona {{newEntries[3].amount}}
             ishlab chiqarish rajalashtirilgan.
          </v-card-text>
          <v-card-title>
            4.Sarmoyaning ishlatilish rejasi
          </v-card-title>
         <v-simple-table>
           <thead>
             <tr>
               <th class="text-left">Sotib olinadigan mulk va <br> xomashyolar</th>
               <th class="text-left">O'lchov birligi</th>
               <th class="text-left">Jami summasi</th>
             </tr>
           </thead>
           <tbody>
             <tr>
               <td class="text-left">  {{newEntries[11].amount}} </td>
               <td class="text-left">Dona</td>
                <td class="text-left">  {{newEntries[12].amount}} so'm</td>
             </tr>
           </tbody>
         </v-simple-table>
        <v-card-text>
          Sotib olinuvchi mol-mulk va xom-ashyolar uchun asosan kredit mablag'lari ajratilgan bo'lib,
           jihoz sotib olish natijasida kredit qoldig'i so'mni tashkil etadi. Qoldiq mablag'lar aylanma
            mablag' uchun ishlatiladi.
        </v-card-text>
        <v-card-title>
          <h3> 5.Maxsulot xizmat va sotish bozori </h3>
          
        </v-card-title>
        <v-card-title>
          Bir oylik ishlab chiqarish hajmi
        </v-card-title>
        <v-simple-table>
           <thead>
             <tr>
               <th class="text-left">Mahsulot </th>
               <th class="text-left">O'lchov birligi</th>
               <th class="text-left">Soni</th>
               <th class="text-left">Summasi </th>
               <th class="text-left">Jami summasi</th>
             </tr>
           </thead>
           <tbody>
             <tr>
               <td class="text-left">  {{newEntries[3].amount}} </td>
               <td class="text-left">Dona</td>
               <td class="text-left"> {{newEntries[15].amount * 24}} </td>
               <td class="text-left"> {{newEntries[13].amount}} so'm</td>
                <td class="text-left">  {{spend}} so'm</td>
             </tr>
           </tbody>
         </v-simple-table>
         <v-card-title>
             Bir oyda sotuv hajmi
           </v-card-title>
          <v-simple-table>
           <thead>
             <tr>
               <th class="text-left">Mahsulot </th>
               <th class="text-left">O'lchov birligi</th>
               <th class="text-left">Soni</th>
               <th class="text-left">Summasi </th>
               <th class="text-left">Jami summasi</th>
             </tr>
           </thead>
           
           <tbody>
             <tr>
               <td class="text-left">  {{newEntries[3].amount}} </td>
               <td class="text-left">Dona</td>
               <td class="text-left"> {{newEntries[16].amount * 24}} </td>
               <td class="text-left"> {{newEntries[14].amount}} so'm </td>
                <td class="text-left">  {{prise}} so'm</td>
             </tr>
           </tbody>
         </v-simple-table>
         <v-card-text>
           Korxonamiz tomonidan ko'rsatilgan xizmatlar va ishlab chiqarish orqali bir oyda {{totalProfit}} so'm foyda ko'rilmoqda. 
           Bundan tashqari korxonamizda {{newEntries[17].amount}} ishchi o'rni yaratilgan bo'lib ularga o'rtacha {{newEntries[18].amount}}
            so'm oylik ish haqi berilmoqda.
            Bundan tashqari mijozlarga o'z vaqtida buyurtma bo'yicha va umumiy tartibda sotish xizmatlarini ko'rsatadi. Ishlab chiqarish
            maxsulotlari hamda uskunalarni sotib olish uchun mol yetkazib beruvchi korxonalar bilan tuzilgan shartnomalar ilova qilinadi.
         </v-card-text>
          <ol id="orderList" >
            <li>Kredit summasi:  {{newEntries[7].amount}} so'm</li>
            <li>Mo'ljallangan foiz: {{newEntries[8].amount}}%  </li>
            <li>Kredit muddati (oy):  {{newEntries[9].amount}} oy </li>
            <li>Kredit foizlari har oyda bir marotaba:  {{parseInt(monthPay) }} so'm</li>
            <li>Asosiy kredit kaytarilishi oylarga teng bo'lingan xolda kaytarib boriladi</li>
            <li>Garovga qo'yiluchi obekt: {{newEntries[10].amount}} </li>
          </ol>
          <v-card-title>
            6.Xulosa
          </v-card-title>
          <v-card-text>
            Bankning xamkorlikdagi faoliyati, kredit mablag'i berish kafolati natijasida, ushbu mablag'ning o'z vaqtida 
            berilishi , uning o'z vaqtida va maksadli foydalanishi, ishlab chikarish xizmati ko'rsatish , ishchi kuchi etarli 
            bo'lgani xolda korxona olingan kredit mablag'ining ustamasi bilan o'z vaqtida qaytarish imkoniyatiga egadir.
             Ushbu mablag'dan foydalanish natijasida o'z aylanma mablag'iga ega bo'ladi, xizmat ko'rsatish orqali aholining 
             ushbu xizmat turlariga bo'lgan talabi nisbatan qondiriladi .
            Bu esa Respublikamizda o'rta va kichik biznesni rivojlantirishda salmoqli xissa qo'shganimiz bo'ladi.
          </v-card-text>
         <div class="d-flex justify-space-between">
           <v-card-text>
             Loyihani ishlab chiqdi <br>
             "{{newEntries[1].amount}}" xususiy korxona boshlig'i:
           </v-card-text>
           <v-card-text>
             {{newEntries[0].amount}}
           </v-card-text>
         </div>
       </div>
      </v-card>
    </div>
  </v-container>
</template>

<script>
export default {
    props: ['newEntries', 'spend', 'prise', 'totalProfit', 'monthPay', 'reports',]
}
</script>

<style scoped>
 #content{
   text-align: center;
 }
 #container{
   width: 80%;
   margin: 0 auto;
 }
 #orderList{
   text-align: left;
 }
</style>