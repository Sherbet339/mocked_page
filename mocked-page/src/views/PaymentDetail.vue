<template>
  <v-container class="payment-detail">
    <v-row>
      <v-col cols="6" md="6" sm="auto">
        <v-card>
          <div class="back-btn">
            <v-icon class="pr-2" size="28">mdi-chevron-left</v-icon>
            <h3>Back</h3>
          </div>
          <div class="deliverd-type">
            <v-radio-group v-model="radios">
              <v-radio color="#7f5df7" value="delivered" label="">
                <template v-slot:label>
                  <div class="radio-label">
                    <v-icon color="#7f5df7">mdi-truck-fast</v-icon>
                    <h4>Get it delivered in only 30 minutes</h4>
                  </div>
                </template>
              </v-radio>
              <v-radio color="#7f5df7" value="pickup">
                <template v-slot:label>
                  <div class="radio-label">
                    <v-icon color="#7f5df7">mdi-basket</v-icon>
                    <h4>Pickup available in 3 stores near you</h4>
                  </div>
                </template>
              </v-radio>
            </v-radio-group>
          </div>

          <h4 style="font-weight: 400" class="mb-2">Shipping address</h4>
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

          <h4 style="font-weight: 400" class="mb-2">Name on card</h4>
          <v-text-field
            style="width: 600px"
            v-model="cardName"
            outlined
            color="#7f5df7"
            dense
          ></v-text-field>

          <h4 style="font-weight: 400" class="mb-2">Card number</h4>
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
              <h4 style="font-weight: 400" class="mb-2">Expiration</h4>
              <v-text-field
                v-model="expiration"
                placeholder="MM/DD"
                outlined
                color="#7f5df7"
                dense
              ></v-text-field>
            </v-col>
            <v-col cols="3" md="3" sm="5">
              <h4 style="font-weight: 400" class="mb-2">CVV</h4>
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
          <v-btn color="#7f5df7" width="265px" dark large
            >Confirm Payment $570.89</v-btn
          >
        </v-card>
      </v-col>
      <v-col cols="auto">
        <v-card>
          <h4>Order Summary</h4>
          <table class="mt-5 mb-3">
            <tr v-for="data in dataTable" :key="data.id">
              <td class="pr-5">{{ data.amount }}</td>
              <td>{{ data.order }}</td>
              <td class="pl-12 pr-4" justify="end">${{ data.price }}</td>
              <td>
                <v-icon>mdi-delete</v-icon>
              </td>
            </tr>
          </table>
          <v-divider class="mb-3"></v-divider>
          <div class="deliveryPrice mb-4">
            <tr>
              <td>Delivery</td>
              <td>$16.99</td>
            </tr>
            <tr>
              <td>Discount</td>
              <td>$0.00</td>
            </tr>
            <v-divider class="my-3"></v-divider>
            <tr>
              <td>Total (exc tax)</td>
              <td>$557.99</td>
            </tr>
            <tr>
              <td>Tax</td>
              <td>$12.99</td>
            </tr>
            <v-divider class="my-3"></v-divider>
            <tr class="order-total">
              <td>Order Total</td>
              <td>$570.98</td>
            </tr>
            <v-divider class="mt-3 mb-4"></v-divider>
            <div class="total-saving">
              <h4>You total saving on this order</h4>
              <h4>$34.99</h4>
            </div>
          </div>
          <v-row>
            <v-col cols="8">
              <v-text-field
                placeholder="Coupon code"
                outlined
                prepend-inner-icon="mdi-ticket"
                color="#7f5df7"
                dense
                hide-details
              ></v-text-field>
            </v-col>
            <v-col>
              <v-btn outlined width="125px" height="40px">Apply</v-btn>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
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
      dataTable: [
        {
          id: 1,
          amount: "x1",
          order: "Franklin Merino Woo V-Neck Knit",
          price: "199.00",
        },
        {
          id: 2,
          amount: "x1",
          order: "Judd Slim Dress Chino Pant",
          price: "159.00",
        },
        {
          id: 3,
          amount: "x1",
          order: "Angus Shawl Chardigan",
          price: "199.99",
        },
      ],
    };
  },
};
</script>