'v-slot' directive doesn't support any modifierとエラーが出たときの対処方法。

[vue/valid-v-slot]
'v-slot' directive doesn't support any modifier.

```vuejs:xxx.vue
 With Eslint error

<template v-slot:item.name="{ item }">
```

```vuejs:xxx.vue
Without error:

<template v-slot:[`item.name`]="{ item }">
```


で解決
