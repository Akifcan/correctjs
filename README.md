# correctjs

A Lightweight validation library for javascript

# Installation

`npm i correctjs`

# Example

```

import { correct } from 'correctjs'
or
const correct = require('correctjs')

    const name = ''
const email = 'test@hotmail'
const age = '109a'
const customReg = '44'
const point = 20
const sayHi = 'hello'
const lentest = 'tttttt'

let check = correct(
    [
        {
            value: name,
            fieldName: 'name',
            validations: [
                {
                    'type': 'required',
                },
                {
                    'type': 'min|5',
                    'message': 'name must be at least 5 character',
                },  
                {
                    'type': 'max|15',
                    'message': 'name not be greater than 15 character'
                },
            ]
        },
        {
            value: email,
            fieldName: 'email',
            validations: [
                {
                    'type': 'required',
                    'message': 'email required'
                },
                {
                    'type': 'max|20',
                    'message': 'email must be at least 5 character'
                },
                {
                    'type': 'email',
                    'message': 'email address format wrong'
                }
            ]
        }, 
        {
            value: age,
            fieldName: 'age',
            validations: [
                {
                    'type': 'required',
                    'message': 'age is required'
                },
                {
                    'type': 'number',
                    'message': 'age must be number'
                },
            ]
        }, 
        {
            value: customReg,
            fieldName: 'custom regex',
            validations: [
                {
                    'type': 'required',
                    'message': 'please enter phone number'
                },
                {
                    'type': 'customRegex|^\\d+$',
                    'message': 'custom regex'
                },
            ]
        }, 
        {
            value: point,
            fieldName: 'point',
            validations: [
                {
                    'type': 'between|10-30',
                    'message': 'point must be between 10 and 20'
                },
            ]
        }, 
        {
            value: sayHi,
            fieldName: 'sayhi',
            validations: [
                {
                    'type': 'required',
                    'message': 'sayhi required'
                },
                {
                    'type': 'startsWith|h',
                    'message': 'must start with h'
                },
            ]
        },
        {
            value: sayHi,
            fieldName: 'sayHi',
            validations: [
                {
                    'type': 'required',
                    'message': 'sayhi required'
                },
                {
                    'type': 'endsWith|o',
                    'message': 'must end with o'
                },
            ]
        },
        {
            value: lentest,
            fieldName: 'len test',
            validations: [
                {
                    'type': 'matchLength|6',
                    'message': 'lentest must be 6 character'
                },
            ]
        },
    ]
)

if(check == true){
    console.log('OK!')
}else{
    console.log(check)
}
```

# Output

`[ 
  'name is required',
  'name must be at least 5 character',
  'email address format wrong',
  'age must be number' 
  ]`

## Commands

* value - value is required
* fieldName - fieldName is required
* message - custom message is optional
* validations - validations is required


* Required - validations: {type: 'required'}
* Min - validations:  {type: 'min|5'}
* Max - validations:  {type: 'max|10'}
* Between - validations: {type: 'between|10-20'}
* CustomRegex - validations: {type: 'customRegex|^\\d+$'}
* StartsWith - validations: {type: 'startsWith|a'}
* EndsWith  - validations: {type: 'endsWith|z'}
* MatchLength  - validations: {type: 'matchLength|5'}
* Email  - validations: {type: 'email'}
* Number - validations: {type: 'number'}

```
   correct(
    [
        {
            value: name,
            fieldName: 'name',
            validations: [
                {
                    'type': 'required',
                },
                {
                    'type': 'min|5',
                    'message': 'name must be at least 5 character',
                },  
                {
                    'type': 'max|15',
                    'message': 'name not be greater than 15 character'
                },
            ]
        }
    ]
```