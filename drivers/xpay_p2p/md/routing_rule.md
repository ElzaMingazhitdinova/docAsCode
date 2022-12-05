# exness-bank-co-w 
### General

| Merchant method  |       Provider channel        |
|------------------|:-----------------------------:|
| exness-bank-co-w | localpayment-bank-co-w-exness |
|                  |   pagsmile-bank-co-w-exness   |

### Routing rule:
1. If document_type == 'PEP' (Permit of Permanence)      <br>
   invoice should be sent to Pagsmile
2. If document_type == 'CC', then
   it should be routed between pagsmile, localpayment and AST-LATAM-BANK-W-01
3. If document_type == 'CE' and length of this document is exact or less than 6 digits, then  <br> 
   it should be routed between pagsmile, localpayment and AST-LATAM-BANK-W-01
4. If document_type == 'CE' and length of this document > than 6 digits, then  <br> 
   it should be routed between pagsmile and AST-LATAM-BANK-W-01
5. If document_types == others <br> 
   it should be routed between localpayment and AST-LATAM-BANK-W-01
