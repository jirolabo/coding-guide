JavaScript
=

- [書き方](#kakikata)

<a id="kakikata">書き方</a>
---

### 全体の書き方


- 全体をfunctionで囲む  
- "use strict;" を追加する

<!-- -->

    (function(global) {
    "use strict;"
    
      // Your Module
      function YourModule() {
          // ...
      };
    
      // Exports
      if ("process" in global) {
          module["exports"] = YourModule;
      }
      global["YourModule"] = YourModule;

    })((this || 0).self || global);


### 数値のフォーマット

 Number の toLocaleString() を使う。


#### +new Date の替わりに Date.now() を使う。

### イベントハンドリングは on() を使用する

[jQuery使いが知っておくべき8つのjQueryテクニック](http://blog.toshimaru.net/jquery-8-tips/)

複数イベントを一つの関数にアタッチできる

    $('#btn').on('click mouseenter', function() {
        alert('clicked! or mouseenter?');
    })

複数のイベントを登録できる

    $('.area').on({
      'mouseenter': function(){ alert('mouse entered!') },
      'mouseleave': function(){ alert('mouse left!') }
    });

３つ目、第二引数にアタッチ先のセレクターを指定することができます。これでなにが嬉しいかというとAJAXなどで遅延して取得してくるような要素に対しても事前にイベントを設定することができます。

    $('#target').on({
      'mouseenter': function(){ alert('mouse entered!') },
      'mouseleave': function(){ alert('mouse left!') }
    }, '.area');
    
    $('#target').html('<div class="area"></div>');

AJAXにはdone()、fail()を使うべし
success, error は使用しない

ajax()だけじゃなくショートカットメソッドも活用すべし

    var data = {
        json: $.toJSON({
            text: 'some text',
            array: [1, 2, 'three'],
            object: {
                par1: 'another text',
                par2: [3, 2, 'one'],
                par3: {}
            }
        })
    }
    
    // 1. ajax()
    $.ajax({
        url:"/echo/json/",
        data:data,
        type:"POST",
        success:function(response) {
           console.log(response);
        }
    });
    
    // 2. post()
    $.post("/echo/json/", data, function(response) {
        console.log(response);
    });

### find()を使って絞り込むべし


. 属性を指定してDOMエレメントを生成できる

    $('<a>', {href: 'http://google.com/', title: 'google'}).text('google')
    [<a href=​"http:​/​/​google.com/​" title=​"google">​google​</a>​ ]

### form送信時はserialize()を使って値をまとめて取得すべし
serialize()を使うことでform内のinputの値をまとめて取得できます。

    $('form').on('submit', function(e) {
        e.preventDefault();
        alert($(this).serialize());
    });
