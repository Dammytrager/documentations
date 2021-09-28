#### PAYSTACK API'S

#### TABLE OF CONTENTS

- [Initiate a charge on a card](#initiate-a-charge-on-a-card)
  - [Charge with Card number and pin](#charge-with-card-number-and-pin)

##### Initiate a charge on a card

If a card is to be charged, paystack provides apis that makes this possible, this could be done in several ways.

###### 1. Charge with Card number and pin

The card will be charged with the card pin sent along with the post data and the card will be debited as soon as paystack returns a success. The request sample is shown below

`url - https://api.paystack.co/charge`

`METHOD - POST`

```
{
  "email":"damilaremalomo@gmail.com",
  "amount":"50000",
  "reference": "new_ref",
  "metadata":{
    "custom_fields":[
      {
        "value":"makurdi",
        "display_name": "Donation for",
        "variable_name": "donation_for"
      }
    ]
  },
  "card":{
    "cvv":"081",
    "number":"507850785078507812",
    "expiry_month":"09",
    "expiry_year":"22"
  },
  "pin": "1111"
}
```

