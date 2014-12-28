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