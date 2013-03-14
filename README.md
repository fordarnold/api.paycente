api.paycente
============

### The PayCente Official REST API - Allows web services to interact with the PayCente platform

This is the first version of the PayCente API.

This platform is, for now, built on Laravel, PHP. Future development will occur with Python,
or any other language that is up to the task of building a REST API easily.

### API Requests

You can send API requests to http://api.paycente.pagodabox.com/ Below are the requests that are handled by the API:
* Incoming Payment
* Outgoing Payment
* Transaction Log

For this demo, we shall not consider users that have access to the API (API User Auth and Permissions).
That will come in version 2 of the API. For now, lets do enough to get a demo API.

### API Responses

These responses are to be returned in JSON format.

#### Incoming Payment
This will tell the API to make a new incoming payment.

**Request**

```bash
POST /payments/incoming/
```

**Response**

```bash
{
  "id": "120012",
  "amount": "120000",
  "currency": "UGX"
}
```

#### Outgoing Payment
This will tell the API to make a new outgoing payment.

**Request**

```bash
POST /payments/outgoing/
```

**Response**

```bash
{
  "id": "110299",
  "amount": "120000",
  "currency": "UGX",
  "paid_to": "256774123456"
}
```

#### Transaction Log
Requests all transaction logs stored with PayCente.

**Request**

```bash
GET /transactions/
```

**Response**

```bash
{
  "2013-03-13": [
    {
      "id": "120012",
      "amount": "120000",
      "currency": "UGX",
      "type": "payments/incoming"
    },
    {
      "id": "110299",
      "amount": "120000",
      "currency": "UGX",
      "type": "payments/outgoing",
      "paid_to": "256774123456"
    }
  ],

  "2013-03-12": [
    {
      "id": "120982",
      "amount": "110000",
      "currency": "UGX",
      "type": "payments/incoming"
    },
    {
      "id": "110299",
      "amount": "120000",
      "currency": "UGX",
      "type": "payments/outgoing",
      "paid_to": "256774123456"
    }
  ]
}
```

## References:

http://net.tutsplus.com/tutorials/php/laravel-4-a-start-at-a-restful-api/

## Installation

* Clone this repo from github.
* In your localhost, run ```bash composer install ```
  This installs composer dependencies needed for the app to run.

* You are ready to go
