JavaScript
=

- [書き方](#kakikata)

<a id="kakikata">書き方</a>
---

### 全体の書き方

1. 全体を (function(){...})(); で囲む
1. "use strict"; を宣言




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

