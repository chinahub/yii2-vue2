yii2 extention based on vue2 in frontend
========================================
yii2 extention based on vue2 in frontend

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist chinahub/yii2-vue2 "*"
```

or add

```
"chinahub/yii2-vue2": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```php
<?php
use allen\Vue;
?>
<?php Vue::begin([
    'id' => "vue-app",
    'data' => [
        'message' => "hello",
        'seen' => false,
        'todos' => [
            ['text' => "aa"],
            ['text' => "akbar"]
        ]
    ],
    'methods' => [
        'reverseMessage' => new yii\web\JsExpression("function(){"
                . "this.message =1; "
                . "}"),
    ]
]); ?>
    
    <p>{{ message }}</p>
    <button v-on:click="reverseMessage">Reverse Message</button>
    
    <p v-if="seen">Now you see me</p>
    
    
    <ol>
        <li v-for="todo in todos">
          {{ todo.text }}
        </li>
    </ol>
    
    <p>{{ message }}</p>
    <input v-model="message">
  
  
<?php Vue::end(); ?>
```

Note
----
it's coding now,Please do not use it in development environment.
about more:read from https://github.com/akbarjoudi/yii2-vue/