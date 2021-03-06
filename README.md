# react-inputs-validation

A react inputs validation component.
# <img src="http://oc54ddm6x.bkt.clouddn.com/react-inputs.gif" />

# Online Demo
Please check the <a href="https://edwardfhsiao.github.io/react-inputs-validation/">online demo example</a>

# Docs Link
[Textbox](#Textbox)

[Radiobox](#Radiobox)

[Checkbox](#Checkbox)

[Select](#Select)

[Textarea](#Textarea)

# Installation
```sh
npm install react-inputs-validation --save
```
# Donate
<a href="https://www.paypal.me/XIAOMENGXIAO/0.99" target="_blank" alt="PayPal Donate">Thanks for donating me a donut!&nbsp;&nbsp;⁄(⁄ ⁄•⁄ω⁄•⁄ ⁄)⁄</a>

# Browser support
Tested on IE9+ and Chrome and Safari(10.0.3)

# Docs

### <a name="Textbox"></a>Textbox

|Props                             |       |Type    |Description                                  |Default     |
|---                               |---    |---     |---                                          |  ---       |
|tabIndex                          |  Opt  |  Str   |                                             |  -1        |
|id                                |  Opt  |  Str   |                                             |  ""        |
|name                              |  Opt  |  Str   |                                             |  ""        |
|type                              |  Opt  |  Str   |                                             |  "text"    |
|value                             |  Opt  |  Str   |                                             |  ""        |
|disabled                          |  Opt  |  Bool  |                                             |  false     |
|placeholder                       |  Opt  |  Str   |                                             |  ""        |
|**validate**                      |**Opt**|**Bool**|**If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.**|**false**   |
|**validationCallback**           |**Opt**|**Func**|**Return the validation result.**|**none**    |
|classNameInput                    |  Opt  |  Str   |                                             |  ""        |
|classNameWrapper                  |  Opt  |  Str   |                                             |  ""        |
|classNameContainer                |  Opt  |  Str   |                                             |  ""        |
|customStyleInput                  |  Opt  |  Obj   |                                             |  {}        |
|customStyleWrapper                |  Opt  |  Obj   |                                             |  {}        |
|customStyleContainer              |  Opt  |  Obj   |                                             |  {}        |
|**onChange**                      |**Req**|**Func**|**(val, e) => {}. Will return the value.**|**(val, e) => {}**|
|**onBlur**                        |**Opt**|**Func**|**In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.**|**none**    |
|onFocus                           |  Opt  |  Func  |                                             |  none      |
|onClick                           |  Opt  |  Func  |                                             |  none      |
|onKeyUp                           |  Opt  |  Func  |                                             |  none      |
|**validationOption**              |**Opt**|**obj** |**validationOption object, see below**|**{}**      |
|**validationOption.name**         |**Opt**|**Str** |**To display in the Error message. i.e Please enter your ${name}.**|**""**      |
|**validationOption.check**        |**Opt**|**Bool**|**To determin if you need to validate.**|**true**    |
|**validationOption.required**     |**Opt**|**Bool**|**To determin if it is a required field.**|**true**    |
|**validationOption.type**         |**Opt**|**Str** |**Validation type, options are ['string', 'number', 'phone'].**|**"string"**|
|**validationOption.showMsg**      |**Opt**|**Bool**|**To determin display the error message or not.**|**true**    |
|**validationOption.min**          |**Opt**|**Num**|**Validation of min length when validationOption['type'] is string, min amount when validationOption['type'] is number.**|**0**       |
|**validationOption.max**          |**Opt**|**Num**|**Validation of max length when validationOption['type'] is string, max amount when validationOption['type'] is number.**|**0**       |
|**validationOption.length**       |**Opt**|**Num**|**Validation of exact length of the value.**|**0**       |
|**validationOption.compare**      |**Opt**|**Str** |**Compare this value to 3 to see if they are equal.**|**""**      |
|**validationOption.reg**          |**Opt**|**Bool**|**Custom regex.**|**""**      |
|**validationOption.regMsg**       |**Opt**|**Str** |**Custom regex error message.**|**""**      |
|**validationOption.locale**       |**Opt**|**Str** |**For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.**|**"en-US"** |
|**validationOption.phoneCountry** |**Opt**|**Str** |**Useful when the validationOption['type'] is phone. Check if the phone number matchs en-US phone number format.**|**"en-US"** |
|**validationOption.msgOnError**   |**Opt**|**Str** |**Show your custom error message no matter what when it has error if it is provied.**|**""**      |
|**validationOption.msgOnSuccess** |**Opt**|**Str** |**Show your custom success message no matter what when it has error if it is provied.**|**""**      |


```js
import { Textbox } from 'react-inputs-validation';

<Textbox
  tabIndex="1" //Optional.[String or Number].Default: -1.
  id={'Name'} //Optional.[String].Default: "".  Input ID.
  name="Name" //Optional.[String].Default: "". Input name.
  type="text" //Optional.[String].Default: "text". Input type [text, password, number].
  value={name} //Optional.[String].Default: "".
  disabled={false} //Optional.[Bool].Default: false.
  placeholder="Place your name here ^-^" //Optional.[String].Default: "".
  validate={validate} //Optional.[Bool].Default: false. If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.
  validationCallback={res =>
    this.setState({ hasNameError: res, validate: false })} //Optional.[Func].Default: none. Return the validation result.
  classNameInput="" //Optional.[String].Default: "".
  classNameWrapper="" //Optional.[String].Default: "".
  classNameContainer="" //Optional.[String].Default: "".
  customStyleInput={{}} //Optional.[Object].Default: {}.
  customStyleWrapper={{}} //Optional.[Object].Default: {}.
  customStyleContainer={{}} //Optional.[Object].Default: {}.
  onChange={(name, e) => {
    this.setState({ name });
    console.log(e);
  }} //Required.[Func].Default: () => {}. Will return the value.
  onBlur={(e) => {console.log(e)}} //Optional.[Func].Default: none. In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.
  // onFocus={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onClick={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onKeyUp={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  validationOption={{
    name: 'Name', //Optional.[String].Default: "". To display in the Error message. i.e Please enter your ${name}.
    check: true, //Optional.[Bool].Default: true. To determin if you need to validate.
    required: true, //Optional.[Bool].Default: true. To determin if it is a required field.
    // type: 'string', //Optional.[String].Default: "string". Validation type, options are ['string', 'number', 'phone'].
    // showMsg: true, //Optional.[Bool].Default: true. To determin display the error message or not.
    // min: 2, //Optional.[Number].Default: 0. Validation of min length when validationOption['type'] is string, min amount when validationOption['type'] is number.
    // max: 10, //Optional.[Number].Default: 0. Validation of max length when validationOption['type'] is string, max amount when validationOption['type'] is number.
    // length: 2, //Optional.[Number].Default: 0. Validation of exact length of the value.
    // compare: '3', //Optional.[String].Default: "" Compare this value to 3 to see if they are equal.
    // reg: /^\d{18}|\d{15}$/, //Optional.[Bool].Default: "" Custom regex.
    // regMsg: 'failed in reg.test(${value})', //Optional.[String].Default: "" Custom regex error message.
    // locale: 'en-US', //Optional.[String].Default: "en-US". For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.
    // phoneCountry: 'en-US', //Optional.[String].Default: "en-US". Useful when the validationOption['type'] is phone. Check if the phone number matchs en-US phone number format.
    // msgOnError: "Your custom error message if you provide the validationOption['msgOnError']", //Optional.[String].Default: "" Show your custom error message no matter what when it has error if it is provied.
    // msgOnSuccess: "Your custom success message if you provide the validationOption['msgOnSuccess']. Otherwise, it will not show, not even green border." //Optional.[String].Default: "". Show your custom success message no matter what when it has error if it is provied.
  }}
/>
```



### <a name="Radiobox"></a>Radiobox

|Props                             |       |Type    |Description                                  |Default     |
|---                               |---    |---     |---                                          |  ---       |
|tabIndex                          |  Opt  |  Str   |                                             |  -1        |
|**id**                            |**Req**|**Str**|**IMPORTANT if you have multiple Radiobox on the page, id is used to distinguish them for the label 'for' use**|**""**      |
|name                              |  Opt  |  Str   |                                             |  ""        |
|value                             |  Opt  |  Str   |                                             |  ""        |
|disabled                          |  Opt  |  Bool  |                                             |  false     |
|**validate**                      |**Opt**|**Bool**|**If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.**|**false**   |
|**validationCallback**           |**Opt**|**Func**|**Return the validation result.**|**none**    |
|**optionList**                    |**Req**|**Array**|**[{id: 'teacher', name: 'teacher']**           |**[]**
|classNameInput                    |  Opt  |  Str   |                                             |  ""        |
|classNameWrapper                  |  Opt  |  Str   |                                             |  ""        |
|classNameContainer                |  Opt  |  Str   |                                             |  ""        |
|classNameOptionListItem           |  Opt  |  Str   |                                             |  ""        |
|customStyleInput                  |  Opt  |  Obj   |                                             |  {}        |
|customStyleWrapper                |  Opt  |  Obj   |                                             |  {}        |
|customStyleContainer              |  Opt  |  Obj   |                                             |  {}        |
|customStyleOptionListItem         |  Opt  |  Obj   |                                             |  {}        |
|**onBlur**                       |**Opt.**|**Func**                  |**In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.**                                                                                                            |**none**     |
|**onChange**                      |**Req.**|**Func**                  |**(val, e) => {}. Will return the value.**|**(val, e)=>{}**   |
|onFocus                           |*Opt.*  |Func                      |                                                                                                            |none     |
|onClick                           |*Opt.*  |Func                      |                                                                                                            |none     |
|**validationOption**              |**Opt**|**obj** |**validationOption object, see below**|**{}**      |
|**validationOption.name**         |**Opt**|**Str** |**To display in the Error message. i.e Please enter your ${name}.**|**""**      |
|**validationOption.check**        |**Opt**|**Bool**|**To determin if you need to validate.**|**true**    |
|**validationOption.required**     |**Opt**|**Bool**|**To determin if it is a required field.**|**true**    |
|**validationOption.showMsg**      |**Opt**|**Bool**|**To determin display the error message or not.**|**true**    |
|**validationOption.locale**       |**Opt**|**Str** |**For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.**|**"en-US"** |
|**validationOption.msgOnError**   |**Opt**|**Str** |**Show your custom error message no matter what when it has error if it is provied.**|**""**      |
|**validationOption.msgOnSuccess** |**Opt**|**Str** |**Show your custom success message no matter what when it has error if it is provied.**|**""**      |

```js
import { Radiobox } from 'react-inputs-validation';

<Radiobox
  tabIndex={2} //Optional.[String or Number].Default: -1.
  id="job" //Optional.[String].Default: "".  Input ID.
  name="job" //Optional.[String].Default: "". Input name.
  disabled={false} //Optional.[Bool].Default: false.
  value={job} //Optional.[String].Default: "".
  validate={validate} //Optional.[Bool].Default: false. If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.
  validationCallback={res =>
    this.setState({ hasJobError: res, validate: false })} //Optional.[Func].Default: none. Return the validation result.
  optionList={JOB_OPTIONS_LIST}
  classNameInput="" //Optional.[String].Default: "".
  classNameWrapper="" //Optional.[String].Default: "".
  classNameContainer="" //Optional.[String].Default: "".
  classNameOptionListItem="" //Optional.[String].Default: "".
  customStyleInput={{}} //Optional.[Object].Default: {}.
  customStyleWrapper={{}} //Optional.[Object].Default: {}.
  customStyleContainer={{
    display: 'flex',
    justifyContent: 'flex-start'
  }} //Optional.[Object].Default: {}.
  customStyleOptionListItem={{ marginRight: '20px' }} //Optional.[Object].Default: {}.
  onChange={(job, e) =>{
    this.setState({ job });
    console.log(e);
  }} //Required.[Func].Default: () => {}. Will return the value.
  onBlur={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onFocus={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onClick={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  validationOption={{
    name: 'Name', //Optional.[String].Default: "". To display in the Error message. i.e Please enter your ${name}.
    check: true, //Optional.[Bool].Default: true. To determin if you need to validate.
    required: true, //Optional.[Bool].Default: true. To determin if it is a required field.
    // showMsg: true, //Optional.[Bool].Default: true. To determin display the error message or not.
    // locale: 'en-US', //Optional.[String].Default: "en-US". For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.
    // msgOnError: "Your custom error message if you provide the validationOption['msgOnError']", //Optional.[String].Default: "". Show your custom error message no matter what when it has error if it is provied.
    // msgOnSuccess: "Your custom success message if you provide the validationOption['msgOnSuccess']. Otherwise, it will not show, not even green border." //Optional.[String].Default: "". Show your custom success message no matter what when it has error if it is provied.
  }}
/>
```






### <a name="Checkbox"></a>Checkbox


|Props                             |       |Type    |Description                                  |Default     |
|---                               |---    |---     |---                                          |  ---       |
|tabIndex                          |  Opt  |  Str   |                                             |  -1        |
|id                                |  Opt  |  Str   |                                             |  ""        |
|name                              |  Opt  |  Str   |                                             |  ""        |
|value                             |  Opt  |  Str   |                                             |  ""        |
|checked                           |  Opt  |  Bool  |                                             |  false      |
|disabled                          |  Opt  |  Bool  |                                             |  false     |
|**validate**                      |**Opt**|**Bool**|**If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.**|**false**   |
|**validationCallback**           |**Opt**|**Func**|**Return the validation result.**|**none**    |
|classNameWrapper                  |  Opt  |  Str   |                                             |  ""        |
|classNameInputBox                 |  Opt  |  Str   |                                             |  ""        |
|classNameContainer                |  Opt  |  Str   |                                             |  ""        |
|customStyleWrapper                |  Opt  |  Obj   |                                             |  {}        |
|customStyleInputBox               |  Opt  |  Obj   |                                             |  {}        |
|customStyleContainer              |  Opt  |  Obj   |                                             |  {}        |
|**onBlur**                       |**Opt.**|**Func**                  |**In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.**                                                                                                            |**none**     |
|**onChange**                      |**Req.**|**Func**                  |**(val, e) => {}. Will return the value.**|**(val, e)=>{}**   |
|onFocus                           |*Opt.*  |Func                      |                                                                                                            |none     |
|onClick                           |*Opt.*  |Func                      |                                                                                                            |none     |
|**labelHtml**                     |*Req.*  |Html                      |                                                                                                            |none     |
|**validationOption**              |**Opt**|**obj** |**validationOption object, see below**|**{}**      |
|**validationOption.name**         |**Opt**|**Str** |**To display in the Error message. i.e Please enter your ${name}.**|**""**      |
|**validationOption.check**        |**Opt**|**Bool**|**To determin if you need to validate.**|**true**    |
|**validationOption.required**     |**Opt**|**Bool**|**To determin if it is a required field.**|**true**    |
|**validationOption.showMsg**      |**Opt**|**Bool**|**To determin display the error message or not.**|**true**    |
|**validationOption.locale**       |**Opt**|**Str** |**For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.**|**"en-US"** |
|**validationOption.msgOnError**   |**Opt**|**Str** |**Show your custom error message no matter what when it has error if it is provied.**|**""**      |
|**validationOption.msgOnSuccess** |**Opt**|**Str** |**Show your custom success message no matter what when it has error if it is provied.**|**""**      |
```js
import { Checkbox } from 'react-inputs-validation';

<Checkbox
  tabIndex="5" //Optional.[String or Number].Default: -1.
  id={'agreement'} //Optional.[String].Default: "".  Input ID.
  name={'agreement'} //Optional.[String].Default: "". Input name
  value={agreement} //Required.[String].Default: "".
  checked={false} //Optional.[Bool].Default: false.
  disabled={false} //Optional.[Bool].Default: false.
  validate={validate} //Optional.[Bool].Default: false. If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.
  validationCallback={res =>
    this.setState({
      hasAgreementError: res,
      validate: false
    })} //Optional.[Func].Default: none. Return the validation result.
  classNameWrapper="" //Optional.[String].Default: "".
  classNameInputBox="" //Optional.[String].Default: "".
  classNameContainer="" //Optional.[String].Default: "".
  customStyleWrapper={{}} //Optional.[Object].Default: {}.
  customStyleInputBox={{}} //Optional.[Object].Default: {}.
  customStyleContainer={{}} //Optional.[Object].Default: {}.
  onBlur={(e) => {console.log(e)}} //Optional.[Func].Default: none. In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.
  // onFocus={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onClick={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  onChange={(agreement, e) => {
    this.setState({ agreement });
    console.log(e);
  }} //Required.[Func].Default: () => {}. Will return the value.
  labelHtml={
    <div style={{ color: '#4a4a4a', marginTop: '2px' }}>
      agree?
    </div>
  } //Required.[Html].Default: none.
  validationOption={{
    name: 'agreement', //Optional.[String].Default: "". To display in the Error message. i.e Please check the ${name}.
    check: true, //Optional.[Bool].Default: true. To determin if you need to validate.
    required: true, //Optional.[Bool].Default: true. To determin if it is a required field.
    // showMsg: true, //Optional.[Bool].Default: true. To determin display the error message or not.
    // locale: 'en-US', //Optional.[String].Default: "en-US". For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.
    // msgOnError: "Your custom error message if you provide the validationOption['msgOnError']", //Optional.[String].Default: "". Show your custom error message no matter what when it has error if it is provied.
    // msgOnSuccess: "Your custom success message if you provide the validationOption['msgOnSuccess']. Otherwise, it will not show, not even green border." //Optional.[String].Default: "". Show your custom success message no matter what when it has error if it is provied.
  }}
/>
```




### <a name="Select"></a>Select

|Props                             |       |Type    |Description                                  |Default     |
|---                               |---    |---     |---                                          |  ---       |
|tabIndex                          |  Opt  |  Str   |                                             |  -1        |
|id                                |  Opt  |  Str   |                                             |  ""        |
|name                              |  Opt  |  Str   |                                             |  ""        |
|type                              |  Opt  |  Str   |                                             |  "text"    |
|value                             |  Opt  |  Str   |                                             |  ""        |
|disabled                          |  Opt  |  Bool  |                                             |  false     |
|**validate**                      |**Opt**|**Bool**|                                             |**false**   |
|**validationCallback**           |**Opt**|**Func**|                                             |**none**    |
|**optionList**                    |**Req**|**Array**|**[{id: '1', name: 'Twin Peaks']**              |**[]**          |
|classNameSelect                   |  Opt  |  Str   |                                             |  ""        |
|classNameWrapper                  |  Opt  |  Str   |                                             |  ""        |
|classNameContainer                |  Opt  |  Str   |                                             |  ""        |
|classNameOptionListContainer      |  Opt  |  Str   |                                             |  ""        |
|classNameOptionListItem           |  Opt  |  Str   |                                             |  ""        |
|customStyleSelect                 |  Opt  |  Obj   |                                             |  {}        |
|customStyleWrapper                |  Opt  |  Obj   |                                             |  {}        |
|customStyleContainer              |  Opt  |  Obj   |                                             |  {}        |
|customStyleOptionListContainer    |  Opt  |  Obj   |                                             |  {}        |
|customStyleOptionListItem         |  Opt  |  Obj   |                                             |  {}        |
|**onChange**                      |**Req**|**Func**|                                             |**(val, e) => {}**|
|**onBlur**                        |**Opt**|**Func**|                                             |**none**    |
|onFocus                           |  Opt  |  Func  |                                             |  none      |
|onClick                           |  Opt  |  Func  |                                             |  none      |
|**selectHtml**                    |**Opt**|**Html**|**The custom html that will display when user choose. Use it if you think the default html is ugly.**|**none**    |
|**selectOptionListItemHtml**      |**Opt**|**Html**|**The custom select options item html that will display in dropdown list. Use it if you think the default html is ugly.**|**none**    |
|**validationOption**              |**Opt**|**obj** |                                             |**{}**      |
|**validationOption.name**         |**Opt**|**Str** |**To display in the Error message. i.e Please enter your ${name}.**|**""**      |
|**validationOption.check**        |**Opt**|**Bool**|**To determin if you need to validate.**|**true**    |
|**validationOption.required**     |**Opt**|**Bool**|**To determin if it is a required field.**|**true**    |
|**validationOption.showMsg**      |**Opt**|**Bool**|**To determin display the error message or not.**|**true**    |
|**validationOption.locale**       |**Opt**|**Str** |**For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.**|**"en-US"** |
|**validationOption.msgOnError**   |**Opt**|**Str** |**Show your custom error message no matter what when it has error if it is provied.**|**""**      |
|**validationOption.msgOnSuccess** |**Opt**|**Str** |**Show your custom success message no matter what when it has error if it is provied.**|**""**      |


```js
import { Select } from 'react-inputs-validation';

<Select
  tabIndex="6" //Optional.[String or Number].Default: -1.
  id={'movie'} //Optional.[String].Default: "". Input ID.
  name={'movie'} //Optional.[String].Default: "". Input name.
  value={movie} //Optional.[String].Default: "".
  disabled={false} //Optional.[Bool].Default: false.
  validate={validate} //Optional.[Bool].Default: false. If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.
  validationCallback={res =>
    this.setState({ hasMovieError: res, validate: false })} //Optional.[Func].Default: none. Return the validation result.
  optionList={MOVIE_OPTIONS_LIST} //Required.[Array of Object(s)].Default: [].
  classNameSelect="" //Optional.[String].Default: "".
  classNameWrapper="" //Optional.[String].Default: "".
  classNameContainer="" //Optional.[String].Default: "".
  classNameOptionListContainer="" //Optional.[String].Default: "".
  classNameOptionListItem="" //Optional.[String].Default: "".
  customStyleSelect={{}} //Optional.[Object].Default: {}.
  customStyleWrapper={{}} //Optional.[Object].Default: {}.
  customStyleContainer={{}} //Optional.[Object].Default: {}.
  customStyleOptionListContainer={{}} //Optional.[Object].Default: {}.
  customStyleOptionListItem={{}} //Optional.[Object].Default: {}.
  onChange={(movie, e) => {
    this.setState({ movie });
    console.log(e);
  }} //Optional.[Func].Default: () => {}. Will return the value.
  onBlur={(e) => {console.log(e)}} //Optional.[Func].Default: none. In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.
  // onFocus={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onClick={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // selectHtml={<div>{movieItem.name}</div>} //Optional.[Html].Default: none. The custom html that will display when user choose. Use it if you think the default html is ugly.
  // selectOptionListItemHtml={MOVIE_OPTIONS_LIST.map(
  //   (i, k) => {
  //     return (
  //       <div
  //         key={k}
  //         onClick={() => {
  //           this.handleMovieChange(i.id);
  //         }}
  //       >
  //         <span className="icon icon-person" />{i.name}
  //       </div>
  //     );
  //   }
  // )} //Optional.[Html].Default: none. The custom select options item html that will display in dropdown list. Use it if you think the default html is ugly.
  validationOption={{
    name: 'movie', //Optional.[String].Default: "". To display in the Error message. i.e Please select a ${name}.
    check: true, //Optional.[Bool].Default: true. To determin if you need to validate.
    required: true, //Optional.[Bool].Default: true. To determin if it is a required field.
    // showMsg: true, //Optional.[Bool].Default: true. To determin display the error message or not.
    // locale: 'en-US', //Optional.[String].Default: "en-US". For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.
    // msgOnError: "Your custom error message if you provide the validationOption['msgOnError']", //Optional.[String].Default: "". Show your custom error message no matter what when it has error if it is provied.
    // msgOnSuccess: "Your custom success message if you provide the validationOption['msgOnSuccess']. Otherwise, it will not show, not even green border." //Optional.[String].Default: "". Show your custom success message no matter what when it has error if it is provied.
  }}
/>
```





### <a name="Textarea"></a>Textarea

|Props                             |       |Type    |Description                                  |Default     |
|---                               |---    |---     |---                                          |  ---       |
|tabIndex                          |  Opt  |  Str   |                                             |  -1        |
|id                                |  Opt  |  Str   |                                             |  ""        |
|name                              |  Opt  |  Str   |                                             |  ""        |
|type                              |  Opt  |  Str   |                                             |  "text"    |
|value                             |  Opt  |  Str   |                                             |  ""        |
|disabled                          |  Opt  |  Bool  |                                             |  false     |
|placeholder                       |  Opt  |  Str   |                                             |  ""        |
|**validate**                      |**Opt**|**Bool**|**If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.**|**false**   |
|**validationCallback**           |**Opt**|**Func**|**Return the validation result.**|**none**    |
|classNameInput                    |  Opt  |  Str   |                                             |  ""        |
|classNameWrapper                  |  Opt  |  Str   |                                             |  ""        |
|classNameContainer                |  Opt  |  Str   |                                             |  ""        |
|customStyleInput                  |  Opt  |  Obj   |                                             |  {}        |
|customStyleWrapper                |  Opt  |  Obj   |                                             |  {}        |
|customStyleContainer              |  Opt  |  Obj   |                                             |  {}        |
|**onChange**                      |**Req**|**Func**|**(val, e) => {}. Will return the value.**|**(val, e) => {}**|
|**onBlur**                        |**Opt**|**Func**|**In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.**|**none**    |
|onFocus                           |  Opt  |  Func  |                                             |  none      |
|onClick                           |  Opt  |  Func  |                                             |  none      |
|onKeyUp                           |  Opt  |  Func  |                                             |  none      |
|**validationOption**              |**Opt**|**obj** |**validationOption object, see below**|**{}**      |
|**validationOption.name**         |**Opt**|**Str** |**To display in the Error message. i.e Please enter your ${name}.**|**""**      |
|**validationOption.check**        |**Opt**|**Bool**|**To determin if you need to validate.**|**true**    |
|**validationOption.required**     |**Opt**|**Bool**|**To determin if it is a required field.**|**true**    |
|**validationOption.type**         |**Opt**|**Str** |**Validation type, options are ['string', 'number', 'phone'].**|**"string"**|
|**validationOption.showMsg**      |**Opt**|**Bool**|**To determin display the error message or not.**|**true**    |
|**validationOption.min**          |**Opt**|**Num**|**Validation of min length when validationOption['type'] is string, min amount when validationOption['type'] is number.**|**0**       |
|**validationOption.max**          |**Opt**|**Num**|**Validation of max length when validationOption['type'] is string, max amount when validationOption['type'] is number.**|**0**       |
|**validationOption.length**       |**Opt**|**Num**|**Validation of exact length of the value.**|**0**       |
|**validationOption.reg**          |**Opt**|**Bool**|**Custom regex.**|**""**      |
|**validationOption.regMsg**       |**Opt**|**Str** |**Custom regex error message.**|**""**      |
|**validationOption.locale**       |**Opt**|**Str** |**For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.**|**"en-US"** |
|**validationOption.msgOnError**   |**Opt**|**Str** |**Show your custom error message no matter what when it has error if it is provied.**|**""**      |
|**validationOption.msgOnSuccess** |**Opt**|**Str** |**Show your custom success message no matter what when it has error if it is provied.**|**""**      |

```js
import { Textarea } from 'react-inputs-validation';

<Textarea
  tabIndex="7" //Optional.[String or Number].Default: -1.
  id="description" //Optional.[String].Default: "".  Textarea ID.
  name="description" //Optional.[String].Default: "". Textarea name.
  value={description} //Optional.[String].Default: "".
  disabled={false} //Optional.[Bool].Default: false.
  placeholder="Place your description here ^-^" //Optional.[String].Default: "".
  validate={validate} //Optional.[Bool].Default: false. If you have a submit button and trying to validate all the inputs of your form at onece, toggle it to true, then it will validate the field and pass the result via the "validationCallback" you provide.
  validationCallback={res =>
    this.setState({
      hasDescriptionError: res,
      validate: false
    })} //Optional.[Func].Default: none. Return the validation result.
  classNameInput="" //Optional.[String].Default: "".
  classNameWrapper="" //Optional.[String].Default: "".
  classNameContainer="" //Optional.[String].Default: "".
  customStyleInput={{}} //Optional.[Object].Default: {}.
  customStyleWrapper={{}} //Optional.[Object].Default: {}.
  customStyleContainer={{}} //Optional.[Object].Default: {}.
  onChange={(description, e) => {
    this.setState({ description });
    console.log(e);
  }} //Required.[Func].Default: () => {}. Will return the value.
  onBlur={(e) => {console.log(e)}} //Optional.[Func].Default: none. In order to validate the value on blur, you MUST provide a function, even if it is an empty function. Missing this, the validation on blur will not work.
  // onFocus={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onClick={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  // onKeyUp={(e) => {console.log(e)}} //Optional.[Func].Default: none.
  validationOption={{
    name: 'Description', //Optional.[String].Default: "". To display in the Error message. i.e Please enter your ${name}.
    check: true, //Optional.[Bool].Default: true. To determin if you need to validate.
    required: true, //Optional.[Bool].Default: true. To determin if it is a required field.
    type: 'string', //Optional.[String].Default: "string". Validation type, options are ['string', 'number', 'phone'].
    // showMsg: true, //Optional.[Bool].Default: true. To determin display the error message or not.
    // locale: 'en-US', //Optional.[String].Default: "en-US". For error message display. Current options are ['zh-CN', 'en-US']; Default is 'en-US'.
    // min: 2, //Optional.[Number].Default: 0. Validation of min length when validationOption['type'] is string, min amount when validationOption['type'] is number.
    // max: 10, //Optional.[Number].Default: 0. Validation of max length when validationOption['type'] is string, max amount when validationOption['type'] is number.
    // length: 2, //Optional.[Number].Default: 0. Validation of exact length of the value.
    // reg: /^\d{18}|\d{15}$/, //Optional.[Bool].Default: "". Custom regex.
    // regMsg: 'failed in reg.test(${value})', //Optional.[String].Default: "". Custom regex error message.
    // msgOnError: "Your custom error message if you provide the validationOption['msgOnError']", //Optional.[String].Default: "". Show your custom error message no matter what when it has error if it is provied.
    // msgOnSuccess: "Your custom success message if you provide the validationOption['msgOnSuccess']. Otherwise, it will not show, not even green border." //Optional.[String].Default: "". Show your custom success message no matter what when it has error if it is provied.
  }}
/>
```
