<template>
  <v-container class="payment-detail">
    <v-row>
      <v-col cols="6" md="6">
        <v-card class="pa-5">
          <div class="back-btn">
            <v-icon class="pr-2" size="28">mdi-chevron-left</v-icon>
            <h4>Back</h4>
          </div>
          <div class="deliverd-type">
            <v-radio-group v-model="radios">
              <v-radio color="#7f5df7" value="delivered" label="">
                <template v-slot:label>
                  <div class="radio-label">
                    <v-icon color="#7f5df7">mdi-truck-fast</v-icon>
                    <h5>Get it delivered in only 30 minutes</h5>
                  </div>
                </template>
              </v-radio>
              <v-radio color="#7f5df7" value="pickup">
                <template v-slot:label>
                  <div class="radio-label">
                    <v-icon color="#7f5df7">mdi-basket</v-icon>
                    <h5>Pickup available in 3 stores near you</h5>
                  </div>
                </template>
              </v-radio>
            </v-radio-group>
          </div>

          <h5 style="font-weight: 400" class="mb-2">Shipping address</h5>
          <v-text-field
            style="width: 600px"
            v-model="address"
            outlined
            append-icon="mdi-pencil"
            color="#7f5df7"
            dense
          ></v-text-field>

          <h4>Payment information</h4>
          <v-btn-toggle
            class="pl-0 mb-4"
            v-model="paymentType"
            color="#7f5df7"
            dense
            group
          >
            <v-btn :value="1">
              <v-img
                src="../assets/img/master-card.png"
                width="35px"
                height="25px"
              >
              </v-img>
            </v-btn>

            <v-btn :value="2">
              <v-img
                src="../assets/img/paypal.jpg"
                width="45px"
                height="30x"
              ></v-img>
            </v-btn>

            <v-btn :value="3">
              <v-img
                src="../assets/img/klarna.png"
                width="40px"
                height="25px"
              ></v-img>
            </v-btn>
          </v-btn-toggle>

          <h5 style="font-weight: 400" class="mb-2">Name on card</h5>
          <v-text-field
            style="width: 600px"
            v-model="cardName"
            outlined
            color="#7f5df7"
            dense
          ></v-text-field>

          <h5 style="font-weight: 400" class="mb-2">Card number</h5>
          <v-text-field
            style="width: 385px"
            v-model="cardNum"
            outlined
            color="#7f5df7"
            dense
          >
            <template #append>
              <v-img
                src="../assets/img/master-card.png"
                width="35px"
                height="25px"
              >
              </v-img>
            </template>
          </v-text-field>

          <v-row justify="flex-start">
            <v-col cols="3" md="3" sm="5">
              <h5 style="font-weight: 400" class="mb-2">Expiration</h5>
              <v-text-field
                v-model="expiration"
                placeholder="MM/DD"
                outlined
                color="#7f5df7"
                dense
              ></v-text-field>
            </v-col>
            <v-col cols="3" md="3" sm="5">
              <h5 style="font-weight: 400" class="mb-2">CVV</h5>
              <v-text-field
                v-model="cvvNum"
                outlined
                color="#7f5df7"
                type="cvv"
                dense
              ></v-text-field>
            </v-col>
          </v-row>

          <v-btn class="mr-4" width="100px" outlined large>Back</v-btn>
          <v-btn color="#7f5df7" width="250px" dark large>Confirm Payment $570.89</v-btn>
        </v-card>
      </v-col>
      <v-col></v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      address: "98 Kile Close, 8-3, Marsfield, Sydney, Australia 2725",
      paymentType: null,
      cardName: "Parham Marandi",
      cardNum: "9383 3847 3494 8763",
      expiration: null,
      cvvNum: 837,
    };
  },
};
</script>