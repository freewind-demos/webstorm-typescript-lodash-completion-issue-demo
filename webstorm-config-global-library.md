Webstorm Config Global Lodash Library
=====================================

NOT needed.

NOT needed.

NOT needed.

Webstorm handles everything perfectly if you use `npm install` not `cnpm install`.

Download by Webstorm
--------------------

If there is no `tsconfig.json` file (you can delete/rename it from this project),
we can configure webstorm to complete lodash as following steps:

![webstorm-lodash-1.jpg](./images/webstorm-lodash-1.jpg)

Make sure the `@types/lodash` library is added:

![webstorm-lodash-2.jpg](./images/webstorm-lodash-2.jpg)

At the mean time, in typescript file, we should do:

```
import * as lodash from 'lodash'
```

We will get lodash completion:

![as-lodash](./images/as-lodash.jpg)

### avoid `import * as _`

But if we import lodash as `_`

```
import * as _ from 'lodash'
```

the completion will not work:

![as-underscore](./images/as-underscore.jpg)

The reason is webstorm will treat the `_` as a `const` or `namespace` whose name is `_`:

![underscore](./images/underscore.jpg)

![underscore-def](./images/underscore-def.jpg)

So we need a different name.

Project WITH `tsconfig.json`
----------------------------

Now let's add the file `tsconfig.json`, and give it empty configuration `{}`.

You will find the lodash completion is broken, there is no completion:

![webstorm-lodash-no-completion.jpg](./images/webstorm-lodash-no-completion.jpg)

<s>No matter how I configure the `tsconfig.json` or webstorm itself, I can't find a way to make the completion work again.</s>

update: use the new way to configure webstorm in [README](./README.md)
