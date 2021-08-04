<p align="center">
  <br>
  <img width="400" src="https://raw.githubusercontent.com/sINusBob/awesome-tips/master/Awesome-DL-002-620x400.jpg" alt="A Little Bit of Awesome Tips">
  <br>
  <br>
</p>

## A Little Bit of Awesome Tips [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sINusBob/awesome-tips)

> For me, a curated list of awesome tips and things. If you don't agree, I'm sorry and thank you =]


#### Vue.js

- Super Simple Way to Add Global Method.
```javascript
/////////////////////////////////////
// In your file that init the Vue app
/////////////////////////////////////
Vue.mixin({
    methods: {
        myGlobalMethod: function (myParam) {
            console.log(myParam);
        },
    }
});

//////////////////////////////////////////////////////
// To run on any other file that is related to the app
//////////////////////////////////////////////////////
this.myGlobalMethod('im ok');
```


#### Vuetify.js

- [File Upload](https://github.com/sINusBob/super-simple-upload-file/) - Super Simple File Upload Component for Vuetify.js.

##### multiple v-checkbox inside v-list-item
- Best and simplest way (for me) to list multiple checkboxes (v-checkbox) within a list (v-list-item).
Objective: I want, when clicking on an item in the list, the checkbox is selected and at the same time, all checkboxes that have been selected are kept in a single model.
```javascript
...
////////////////////////////////////////////////////////////////////////
//
////////////////////////////////////////////////////////////////////////
data() {
    return {
        checkboxes: [
            {id: 1, name: 'name1'},
            {id: 2, name: 'name2'},
            {id: 3, name: 'name3'},
        ],

        settings: [],
    }
},
...
////////////////////////////////////////////////////////////////////////
//
////////////////////////////////////////////////////////////////////////
watch: {
    settings(newValue, oldValue) {
        console.log(newValue, oldValue)
    },
},
...
```

```html
<!-- v-list flat: I don't want the item to have the selected effect, only the checkbox -->
<v-list flat>
<!--   the magic, simple as it is, is here (v-model="settings" & :value="item") -->
    <v-list-item-group multiple v-model="settings" active-class="no-active">
        <template v-for="(item, idx) in checkboxes">
            <v-list-item
                :key="idx"
                :value="item"
            >
                <template v-slot:default="{ active }">
                    <v-list-item-action>
                        <v-checkbox :input-value="active"></v-checkbox>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>{{item.name}}</v-list-item-title>
                    </v-list-item-content>
                </template>
            </v-list-item>
        </template>
    </v-list-item-group>
</v-list>
```

```css
/* css totally optional */

/* disable ripple effect */
>>>.v-ripple__container {
    display: none !important;
}

/* disable selected item effect, however the 'flat' prop seems to be better */
.no-active::before{

    /* seems to be better with this */
    opacity: 0 !important;
    
    /*background-color: transparent !important;*/
}

```

#### Javascript

- Estados do Brasil em um Javascript Array
```javascript
const uf = [
  {'uf': 'AC', 'estado': 'Acre'},
  {'uf': 'AL', 'estado': 'Alagoas'},
  {'uf': 'AP', 'estado': 'Amapá'},
  {'uf': 'AM', 'estado': 'Amazonas'},
  {'uf': 'BA', 'estado': 'Bahia'},
  {'uf': 'CE', 'estado': 'Ceará'},
  {'uf': 'DF', 'estado': 'Distrito Federal'},
  {'uf': 'ES', 'estado': 'Espírito Santo'},
  {'uf': 'GO', 'estado': 'Goías'},
  {'uf': 'MA', 'estado': 'Maranhão'},
  {'uf': 'MT', 'estado': 'Mato Grosso'},
  {'uf': 'MS', 'estado': 'Mato Grosso do Sul'},
  {'uf': 'MG', 'estado': 'Minas Gerais'},
  {'uf': 'PA', 'estado': 'Pará'},
  {'uf': 'PB', 'estado': 'Paraíba'},
  {'uf': 'PR', 'estado': 'Paraná'},
  {'uf': 'PE', 'estado': 'Pernambuco'},
  {'uf': 'PI', 'estado': 'Piauí'},
  {'uf': 'RJ', 'estado': 'Rio de Janeiro'},
  {'uf': 'RN', 'estado': 'Rio Grande do Norte'},
  {'uf': 'RS', 'estado': 'Rio Grande do Sul'},
  {'uf': 'RO', 'estado': 'Rondônia'},
  {'uf': 'RR', 'estado': 'Roraíma'},
  {'uf': 'SC', 'estado': 'Santa Catarina'},
  {'uf': 'SP', 'estado': 'São Paulo'},
  {'uf': 'SE', 'estado': 'Sergipe'},
  {'uf': 'TO', 'estado': 'Tocantins'},
];
```


#### MSDOS

- How get/display the date/time in ISO 8601 format
```
@echo off
FOR /F "skip=1 tokens=1-6" %%G IN ('WMIC Path Win32_LocalTime Get Day^,Hour^,Minute^,Month^,Second^,Year /Format:table') DO (
   IF "%%~L"=="" goto s_done
      SET _yyyy=%%L
      SET _mm=00%%J
      SET _dd=00%%G
      SET _hour=00%%H
      SET _minute=00%%I
      SET _second=00%%K
)

:s_done
:: Pad digits with leading zeros
      SET _mm=%_mm:~-2%
      SET _dd=%_dd:~-2%
      SET _hour=%_hour:~-2%
      SET _minute=%_minute:~-2%
      SET _second=%_second:~-2%

:: Display the date/time in ISO 8601 format:
ECHO.
SET _isodate=%_yyyy%-%_mm%-%_dd% %_hour%:%_minute%:%_second%
ECHO %_isodate%
```


#### Generator

 - [Avast Password Generator](https://www.avast.com/random-password-generator) - Best Free Random Password Generator.
 - [LastPass Password Generator](https://www.lastpass.com/pt/password-generator) - Another Best Free Random Password Generator.
 - [Wheel of Names](https://wheelofnames.com) - Nice Random Name Picker.


#### AutoHotkey

- [Resize and Move Window](https://github.com/sINusBob/https://github.com/sINusBob/AutoHotkey-Super-Simple-Script-Resize-and-Move-Active-Window) - AutoHotkey Super Simple Script Resize and Move Active Window.





#### Github

- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) - GitHub Markdown Quick Reference and Showcase


#### Formulas

- How did I measure the performance increase?
```javascript
((old - new) / old) * 100%
= ((20 sec - 5 sec) / 20 sec) * 100%
= 75 % (performance increase) 
```

#### PHPSTORM

- [Autocompletion Webpack Path](https://stefanbauer.me/tips-and-tricks/autocompletion-for-webpack-path-aliases-in-phpstorm-when-using-laravel-mix) - How Autocompletion for Webpack path aliases in PhpStorm when using Laravel Mix
- PHPSTORM hide cursor while typing. Setting ide.hide.cursor.when.typing custom property to false (Help->Edit Custom Properties..) will disable the feature
```
ide.hide.cursor.when.typing=false
```


#### Under development

*That's so 2000s ...*
