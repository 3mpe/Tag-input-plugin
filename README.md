# Dropdown

JQuery key value select tag input


## Support
- Internet Explorer 8+
- Chrome
- Safari
- Firefox

## Based
- jQuery 1.4+


## Example 


```json
[
    {
      "id": 1, 
      "disabled": false, 
      "groupName"
      "groupId": 3,
      "selected": false, 
      "name": "Test" 
    },
    {
      "id": 2,
      "disabled": false,
      "groupName": "Test",
      "groupId": 2,
      "selected": false,
      "name": "Test User"
    }
]
```

## Options
|  | Type| Default value|
| ----            |-----      |-----        |
| readOnly          |Boolean    |`false`
|limitCount         |Number     |`Infinity`
| input           |HTML     |`<input type="text" maxLength="20" placeholder="">`
| data            |Array      |`[]`
| searchable        |Boolean    |`true`
| searchNoData        |HTML     |`<li style="color:#ddd">Not found</li>`
| choice          |Function   | `function(){}`
| init            |Function   | `function(){}`
| extendProps       |Array      | `['prop1','prop2']`





### changeStatus(status)
```js
var dropdown = $('selector').dropdown(options).data('dropdown');
dropdown.changeStatus('readonly') // readonly
dropdown.changeStatus('disabled') // disabled
dropdown.changeStatus() // cancel

```

### choose(value,status)



```js
var dropdown = $('selector').dropdown(options).data('dropdown');
dropdown.destroy();

```

### update(Array,isCover)

### destroy()

```js
var dropdown = $('selector').dropdown(options).data('dropdown');
dropdown.destroy();

```

### reset()
```js
var dropdown = $('selector').dropdown(options).data('dropdown');
dropdown.reset();

```

## Usage

```html
<script src="http://cdn.bootcss.com/jquery/1.8.1/jquery.js"></script>
<link rel="stylesheet" type="text/css" href="./jquery.dropdown.css">
<script src="./jquery.dropdown.js"></script>
```


```html
<div class="dropdown-mul-1">
  <select style="display:none"  name="" id="" multiple>
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
      <option value="4">4</option>
      <option value="5">5</option>
      <option value="6">6</option>
      <option value="7">7</option>
      <option value="8">8</option>
      <option value="9">9</option>
      <option value="10">10</option>
      <option value="11">11</option>
      <option value="12">12</option>
  </select>
</div>
```

```js
$('.dropdown-mul-1').dropdown({
  limitCount: 40,
  multipleMode: 'label',
  choice: function () {
    console.log(arguments,this);
  }
});
```




###### OR


```js

// tag input
function initTagInput(id, param, calback) {

    var params = param || {};
    var item = $(id);
    item.append('<select style="display:none" name="" id="id' + id + '-select" multiple></select>');
    var selectItem = item.find('select');

    var tagsInput = $(id).dropdown({
        readOnly: params.readOnly || false,
        multipleMode: params.multipleMode || 'label',
        limitCount: params.limitCount || 3,
        input: params.input || '<input type="text" maxLength="20" placeholder="Arama Yap">',
        data: params.data || dropDownData,
        searchable: params.searchable || true,
        searchNoData: params.searchNoData || '<li style="color:#ddd">Sonuc Bulunamadi</li>',
        choice: function ($el, value) {
            if (typeof calback === "function") {
                calback(selectItem.val());
            }
        }
    });

}

  
  initTagInput(".clasName", { data: data, limitCount: data.length }, callback);
```
