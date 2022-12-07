#  Requirements for 

**FR.1** 
1. Merchant method -{}
2. Provider channel  
3. MID {URL to psp-team BO} 
___
**FR.2** **Requirements for the payment flow**
 1. REDIRECT
 2. FINAL FORM
 3. COLLECT DATA + REDIRECT
 4. COLLECT DATA + FINAL FORM
 5. S2S (direct)
 6. СС (cards)
 7. Collect data can be:
    1. ONE STEP
    2. MULTI-STEP

---
**FR.3** **Routing rules**

___
**FR.4** **Requirements for the first step of [payment][withdrawal] form**

1. System shall pre-fill the form according to the last accepted [deposit][withdrawal] invoice of the user.
2. System shall return the following title on the form: “Deposit via mobile money“
3. System shall return the disclaimer with the following text on the form: “If you did not receive the PUSH confirmation please complete the payment by dial 1234 ”
4. System shall return the following fields on the form:
   1. Bank name
   2. Account number
   3. Account name
5. System shall sort fields on the form in following way:
 >bank_name </br>
bank_code </br>
swift_code </br>
bank_area </br>
bank_province </br>
bank_city </br>
branch_name </br>
branch_code </br>
mobile_operator </br>
account_type </br>
receive_method </br>
crypto_currency </br>
account_number </br>
iban </br>
wallet_id </br>
phone </br>
email </br>
crypto_address </br>
account_name </br>
card_number </br>
card_holder </br>
expire_date </br>
first_name </br>
last_name </br>
client_name </br>
birth_date </br>
client_postal_code </br>
client_city </br>
client_address_line1 </br>
client_address_line2 </br>
document_type </br>
document_number </br>
voucher </br>
reference_id </br>
 ___
6. Requirements for the field ‘Bank name’
> {
                'name': 'bank_code', </br>
                'title': 'Bank name', </br>
                'type': 'select', </br>
                'options': await self.get_banks() </br>
            }
___
7. The following banks should be added in the deny list in provider channel by default
___
8. Requirements for the field ‘Account number'
>{
                'name': 'account_number', </br>
                'title': 'Account number', </br>
                'type': 'text', </br>
                'validator': '', </br>
                'mask': '' </br>
                'caption': '' </br>
                'dependencies: dependency</br>
            }
___
9. _Only if field has dependency_
Description of dependency for the field 'Account number'
> 'defaultVisibility': False, </br>
'dependencies': { </br>
                'rules': [ </br>
                    {
                        'name': 'bank_code', </br>
                        'values': [constants.ZENITH_BANK_CODE],</br>
                        'visibility': True,</br>
                    }</br>
                ]</br>
            }</br>
___
5. **Requirements for the final form**
___
_Put here information about title and body of final form if it’s custom final form_
___
6. **Requirements for payment info**
 1. System shall send the following data in payment info to the merchant
* ['account_number'] from params['account_number']
* ['mobile_operator'] from deposit response data.network

2. System shall return the following data in payment info on the final form:
* Bank name
* Account number
* Account name
___
**FR.7 Requirements for error procedure**

1. In case of failed synchronous response, System shall send the following parameters in DWH:
* decline_code: {source}
* decline_message : {source}

2. In case of failed get_status, System shall send the following parameters in DWH:
* decline_code: {source}
* decline_message : {source}
___

**FR.8** **Other functional requirements**
1. Requirement for follow_status
_If there is no follow_status, clarify that explicitly_
2. System shall send invoice.local_amount as integer number/fractional number
3. System shall mask the value for the following parameters in logs:  </br>
For example: </br>
* merchant_id and merchant_password in the ‘Create a new deposit’ request
* token the ‘Get JWT token’ response
---
**FR.9** **Requirements for the provider’s side on mobile devices** </br>
_If any function need to be checked on WebView, iOS here details.
Example: When the client clicks the button ‘Download’ System shell save picture in gallery_

# Non-functional requirements
**NFR.1** UI should has localization into English (en) and {additional language code}
