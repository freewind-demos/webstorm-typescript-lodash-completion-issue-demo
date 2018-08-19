TypeScript Lodash Import All Demo
=================================

Import all methods from lodash rather than a single method.

```
npm install
npx ts-node hello.ts
```

It will print `Hello, TypeScript!`

To work with WebStorm completion
--------------------------------

如果想使用WebStorm的提示功能，有一点需要注意：

```
import * as lodash from 'lodash'
```

这里的`* as lodash`不能写成`* as _`，否则什么也提示不出来。

![as-lodash](./images/as-lodash.jpg)

![as-underscore](./images/as-underscore.jpg)

原因在于，如果我们`* as _`，WebStorm会错误的把`_`指向lodash中已经定义了的`_`:

![underscore](./images/underscore.jpg)

![underscore-def](./images/underscore-def.jpg)

所以我们需要使用一个不同的名字。