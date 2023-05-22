#  API for P2P in KH [d] 
### API reference
https://bo.transfer1515.com/apidoc/XPayDeposit_EN.html

### Status model

| Provider |   Gatech   | Comment |
|----------|:----------:|---------|
| 001      | Processing |         |
| 111      |  Accepted  |         |

### Credentials
>merchant_api: super_merchant<br/>
merchant_key: super_key

### Signature
Creating the signature string (SHA1 Hash):

1. Apart from the signature field, all the parameters to be used to generate a signature will follow the order in which the parameters are listed in the tables below.
2. The format of the string follows QueryString format (i.e. key1=value1&key2=value2….) and concatenated without any spaces. All empty values do not need to be added when generating the signature.
3. All values and keys used in the signature string are as is. Please do not perform URL encoding on these strings.

Example:<br/>
>**input string** <br/>
partner_code=EX00001&partner_orderid=asd993asda&member_id=member123&currency=JPY&amount=1000000&account_name=黄晓明&bank_code=MMJJP&notify_url=https://leshukov.free.beeceptor.com&key=XXXXXXX<br/>
**output string** <br/>
739F9D3A01910AB4807ECE440A418FA003833017

### Description of requests
#### Request ‘Create a new deposit'
##### Description of request
| **URL**      | **https://www.paymentonline515.com/fundtransfer.php** |
|--------------|:-----------------------------------------------------:|
| HTTP Method  |                         POST                          |
| Content-Type |           application/x-www-form-urlencoded           |

| **Parameter** |  **Type**   | **Description**                                                                          | **Source**              |
|---------------|:-----------:|------------------------------------------------------------------------------------------|-------------------------|
| notify_url    | String(255) | This is the URL that will be used to notify of successful transactions status            | callback_url            |
| partner_code  |  String(7)  | The partner code assigned in the system. The code is normally 7 alphanumeric characters. | credentials.merchant_id |
| member_id     |  String(35  | The member that is currently doing the transaction name                                  | invoice.client_id       |
' \
--data-urlencode 'member_id=member123' \
--data-urlencode 'currency=JPY' \
--data-urlencode 'amount=1000000' \
--data-urlencode 'account_name=黄晓明' \
--data-urlencode 'bank_code=MMJJP' \
--data-urlencode 'notify_url=https://leshukov.free.beeceptor.com' \
--data-urlencode 'sign=739F9D3A01910AB4807ECE440A418FA003833017'
>
### Description of response

| **Parameter**   |  **Type**  | **Description**  |
|-----------------|:----------:|------------------|
| billno          | String(7)  | provider trx_id  |
| partner_orderid | String(20) | our trx_id       |
| currency        | String(3)  | invoice.currency |
