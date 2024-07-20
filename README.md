# This contract code to test PAAS marlowe compiler output:
{
"when": [
{
"case": {
"deposits": 75000000,
"into_account": {
"role_token": "Seller"
},
"of_token": {
"currency_symbol": "",
"token_name": ""
},
"party": {
"role_token": "Buyer"
}
},
"then": {
"timeout": 1710418041000,
"timeout_continuation": "close",
"when": [
{
"case": {
"choose_between": [
{
"from": 0,
"to": 0
}
],
"for_choice": {
"choice_name": "Everything is alright",
"choice_owner": {
"role_token": "Buyer"
}
}
},
"then": "close"
},
{
"case": {
"choose_between": [
{
"from": 1,
"to": 1
}
],
"for_choice": {
"choice_name": "Report problem",
"choice_owner": {
"role_token": "Buyer"
}
}
},
"then": {
"from_account": {
"role_token": "Seller"
},
"pay": 75000000,
"then": {
"timeout": 1710421641000,
"timeout_continuation": "close",
"when": [
{
"case": {
"choose_between": [
{
"from": 1,
"to": 1
}
],
"for_choice": {
"choice_name": "Confirm problem",
"choice_owner": {
"role_token": "Seller"
}
}
},
"then": "close"
},
{
"case": {
"choose_between": [
{
"from": 0,
"to": 0
}
],
"for_choice": {
"choice_name": "Dispute problem",
"choice_owner": {
"role_token": "Seller"
}
}
},
"then": {
"timeout": 1710425241000,
"timeout_continuation": "close",
"when": [
{
"case": {
"choose_between": [
{
"from": 0,
"to": 0
}
],
"for_choice": {
"choice_name": "Dismiss claim",
"choice_owner": {
"role_token": "Mediator"
}
}
},
"then": {
"from_account": {
"role_token": "Buyer"
},
"pay": 75000000,
"then": "close",
"to": {
"account": {
"role_token": "Seller"
}
},
"token": {
"currency_symbol": "",
"token_name": ""
}
}
},
{
"case": {
"choose_between": [
{
"from": 1,
"to": 1
}
],
"for_choice": {
"choice_name": "Confirm claim",
"choice_owner": {
"role_token": "Mediator"
}
}
},
"then": "close"
}
]
}
}
]
},
"to": {
"account": {
"role_token": "Buyer"
}
},
"token": {
"currency_symbol": "",
"token_name": ""
}
}
}
]
}
}
]
}
