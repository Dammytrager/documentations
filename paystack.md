### PAYSTACK API'S

### TABLE OF CONTENTS

- [Initiate a charge on a card](#initiate-a-charge-on-a-card)
  - [Charge with Card number and pin](#charge-with-card-number-and-pin)
  - [Initiate charge on a card and pin and/or OTP will be sent separately](#initiate-charge-on-a-card-and-pin-and-otp-will-be-sent-separately)
  - [Send PIN to complete a charge or go to next step](#send-pin-to-complete-a-charge-or-go-to-next-step)
  - [Send OTP to complete a charge or go to next step](#send-otp-to-complete-a-charge-or-go-to-next-step)
  - [Check Charge Status](#check-charge-status)

#### Initiate a charge on a card

If a card is to be charged, paystack provides apis that makes this possible, this could be done in several ways.

#### Charge with Card number and pin

The card will be charged with the card pin sent along with the post data and the card will be debited as soon as paystack returns a `success` in the `data.status` response. The request sample is shown below.

[paystack](https://paystack.com/docs/api/#charge-create)

`url - https://api.paystack.co/charge`

`METHOD - POST`

```json
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



#### Initiate charge on a card and pin and OTP will be sent separately

The charge endpoint will be called with the card details and paystack will respond with the `transaction_reference` and  next steps in the `data.status` response. The next steps could be `send_pin` or `send_otp` . This will initiate the charge but the card will not be debited until any of the next steps is completed. In the body the `pin` will not be sent as part of the request data

[paystack](https://paystack.com/docs/api/#charge-create)

`url - https://api.paystack.co/charge`

`METHOD - POST`

```json
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
  }
}
```



#### Send PIN to complete a charge or go to next step

The submit pin endpoint is a next step from the [inititiate charge](#initiate-charge-on-a-card-and-pin-and-otp-will-be-sent-separately) endpoint, the pin of the card that a charge was initaited on and the transaction reference will be sent to paystack, if the card requires an otp or other forms of confirmation after the pin it will be in the `data.status` response from paystack (e.g, `send_otp`). If the card does not require any next step, the card will be debited and paystack will return a success in the `data.status` response.

[paystack](https://paystack.com/docs/api/#charge-submit-pin)

`url - https://api.paystack.co/charge/submit_pin`

`METHOD - POST`

```json
{
    "pin": "1111",
    "reference": "new_ref"
}
```



#### Send OTP to complete a charge or go to next step

The send otp endpoint is a next step from the [send pin](#send-pin-to-complete-a-charge-or-go-to-next-step) endpoint, the otp paystack sent to the client for the card to be charged and the transaction reference will be sent to paystack, If the card does not require any next step, the card will be debited and paystack will return a success in the `data.status` response.

[paystack](https://paystack.com/docs/api/#charge-submit-otp)

`url - https://api.paystack.co/charge/submit_otp`

`METHOD - POST`

```json
{
    "otp": "123456",
    "reference": "new_ref"
}
```



#### Check Charge Status

Paystack provides an endpoint to check a charge status. The reference of the charge is passed in the path parameter

[paystack](https://paystack.com/docs/api/#charge-check)

`url - https://api.paystack.co/charge/:reference`

`METHOD - GET`