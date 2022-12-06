#  Requirements for P2P in KH [d] 
| **ID** |                                      **Description**                                       | **Reference** |
|--------|:------------------------------------------------------------------------------------------:|---------------|
| FR.1   |               Merchant method - https://backoffice.stage.gt.env/methods/show               |               |
| FR.2   |           Provider channel - https://backoffice.stage.gt.env/channels/6797/show            |               |
| FR.3   |                             Requirements for the payment flow                              |               |
| FR.4   |                    Requirements for the second step of the payment form                    |               |
| FR.5   | System shall pre-fill the form according to the last accepted deposit invoice of the user. |               |
| FR.5.1 |           System shall return the following title on the form: "Make a deposit"            |               |

<div hidden>
@startuml ErrorDiagram
!pragma useVerticalIf on
start
:Create a Deposit;
if (http_code == 2XX?) then (no)
 :Move to Fail;
 stop
 elseif (Did we get redirect URL?) then (yes);
  :Go to the next step;
  stop
 else (no) 
:Move to Fail and send msg to sentry;
stop
@enduml
</div>

![](ErrorDiagram.svg)