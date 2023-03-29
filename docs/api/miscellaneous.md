---
sidebar_position: 7
---

# Miscellaneous

## GET `/legal/{languageCode?}`

The **GET** `/legal` will retrieve content of the terms and conditions for a specified language code.

#### Headers

* **Accept**: `application/json`

#### Route Parameters

* **`languageCode`**: The parameter specify the language code of the terms and conditions to retrieve.

 ***Examples***: `en`, `en-us`, `de`, `nl`, `sv`

#### Response Examples

* **Code 200** Success
 ```json
{
  "success": true,
  "data": {
    "title": "User Agreement",
    "sections": [
      {
        "title": "User Agreement",
        "content": "<p>H&C TV Limited (“H&C”), provides a video subscription service that allows members to access live and on demand equestrian sports content and other equestrian related programming (the “H&C Services” or the “Services”), streamed over the internet to certain internet-connected TVs, computers and other devices.\n</p>\n<p>Please read this User Agreement before subscribing for the Services. You acknowledge that you have read and understood and agree with these conditions now and every time you use the Services, and you accept any revised version.</p>"
      },
      {
        "title": "Data Policy",
        "content": "<p>We are committed to protecting the privacy of users of the H&amp;C Services. This Data Privacy Policy explains what information we may collect about you, how we will use it and the steps that we will take to ensure that such information is kept secure, in compliance with the General Data Protection Regulation (EU) 2016/679.&nbsp;By using the Services, you consent to us collecting and using your details in accordance with this Data Privacy Policy.</p>\n<p>When you use the Services, we may collect details about you (“Personal Information”), which may consist of your contact details (such as your name or e-mail address) or other anonymized information about you such as your computer’s IP address. Such details are collected in a number of ways: they can be obtained via the use of cookies or when you register to purchase a particular product or service from us.</p>"
      },
      {
        "title": "Cookies",
        "content": "<p>Cookies are small text files that are shared between your computer and a website. We use cookies on the website to know if you are logged in to the website, and also to gather anonymous information about the pages you visit so that we can provide the best possible service. For more information about cookies, <a href=\"https://en.wikipedia.org/wiki/HTTP_cookie\" target=\"_blank\" rel=\"noopener noreferrer\">click here</a>.</p>"
      }
    ]
  }
}
 ```
* **Code 404** Failure
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```
