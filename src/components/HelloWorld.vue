<template>
  <v-container>
    <v-card>
      <v-row>
        <v-col cols="5">
          <v-simple-table>
            <template v-slot:default borderless>
              <tbody>
                <tr><br></tr>
                <tr>
                  <td>Total<strong> Members :</strong></td>
                  <td style="text-align: right;">{{ summarytier.total_members }}</td>
                </tr>
                <tr>
                  <td>Total<strong> Rev. </strong><small>(THB)</small> :</td>
                  <td style="text-align: right;">{{ summarytier.total_amount }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-col> <!-- left -->
        
        <v-col cols="7">
          <v-simple-table>
            <template v-slot:default borderless>
              <p class="m">{{ summarytier.tier_name }}</p>
              <tbody>
                
                <tr>
                  <td>Total<strong> Members :</strong></td>
                  <td style="text-align: right;">{{ summarytier.total_members }}</td>
                </tr>
                <tr>
                  <td>Total<strong> Rev. </strong><small>(THB)</small> :</td>
                  <td style="text-align: right;">{{ summarytier.total_amount }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-col> <!-- right -->
      </v-row>
    </v-card>
    
    <v-data-table
      :headers="headers"
      :items="items"
    >
    </v-data-table>

    <v-col cols="12">
      <v-simple-table dark>
        <tbody>
          <tr>
            <td>Total</td>
            <td></td>
            <td></td>
            <td>{{ summarytier.total_amount }}</td>
            <td>7</td>
            <td>{{ summary.totalpoint }}</td>
            <td>{{ summary.remainingpoint}}</td>
          </tr>
        </tbody>
      </v-simple-table>
    </v-col>
  </v-container>


</template>

<script>
  export default {
    name: 'HelloWorld',
    
    data: () => ({
    valid: true,
    dialog: false,
    headers: [
      {
        text: "Name",
        value: "customername"
      },
      {
        text: "ID",
        value: "customerphone"
      },
      {
        text: "Tier",
        value: "customertier"
      },
      {
        text: "LTV",
        value: "totalamount"
      },
      {
        text: "Total Trans.",
        value: "totaltransaction"
      },
      {
        text: "Total Point",
        value: "totalreward"
      },
      {
        text: "Remaining Point",
        value: "remainingpoint"
      }
    ],
    items: [],
    summarytier: {
      total_members: 5,
      total_amount: 639489, //731899
      tier_name: "Platinum"
    },
    summary: {
      totaltransaction: 5,
      totalpoint: 47699,
      remainingpoint: 47669, //89983
      lifetimevalu: 985339
    },
    total: { total: 5 }
  }),
  created() {
    this.initialize();
  },
  methods: {
    initialize() {
      this.items = [
        {
          customername: "Bussaracum",
          customerphone: "0824669224",
          customertier: "Gold",
          totalamount: 500008,
          totaltransaction: 1,
          totalreward: 40000,
          remainingpoint: 40000
        },
        {
          customername: "Leelar",
          customerphone: "0874368466",
          customertier: "Platinum",
          totalamount: 10000,
          totaltransaction: 1,
          totalreward: 800,
          remainingpoint: 800
        },
        {
          customername: "Papawarin M.",
          customerphone: "0900843048",
          customertier: "Silver",
          totalamount: 111050,
          totaltransaction: 3,
          totalreward: 4442,
          remainingpoint: 4442
        },
        {
          customername: "VeryCust",
          customerphone: "0199909999",
          customertier: "White",
          totalamount: 8600,
          totaltransaction: 1,
          totalreward: 2064,
          remainingpoint: 2064
        },
        {
          customername: "smilecustomer",
          customerphone: "0187773377",
          customertier: "Black",
          totalamount: 9840,
          totaltransaction: 1,
          totalreward: 393,
          remainingpoint: 393
        },
      ];
    },
  }
};
</script>

<style lang="scss">
thead span {
  color: white;
  font-size: 16px;
  font-weight: 400;
}
.v-data-table-header {
  background-color: grey;
}
.v-card {
  margin-top: 15px;
  margin-bottom: 20px;
}
.m {
  margin-left: 280px;
}
</style>