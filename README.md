# Documentation for `toConstOpti`

_Generated using `spwn doc [file name]` with some revision_

## Exports

```spwn
{
    toConstOpti: ( /* ... */ ) { /* ... */ }
}
```

**Type:** `@dictionary`

## Macros

### toConstOpti

>Macro you need to execute at the start(on compile time) to prepare the trigger. it will return a trigger function which you could run on runtime
>```spwn
>toConstOpti = (
>   counter     : (@counter | @item),
>   trig        : @object,
>   key         : @object_key,
>   range       : @range        = 0..1024,
>   multiplier  : @number       = 1
> ){ /* ... */ }
>```
>
>**Type:** `@macro`
>
>**Example:**
>
>```spwn
>number = counter(1i)
>alphaTrig = alpha_trigger(1g,0,0.5)
>run = toConstOpti(number, alphaTrig, OPACITY, multiplier = 0.01)
>
>rotateTrig = rotate_trigger(100g,101g,0,2)
>execute = toConstOpti(2i,rotateTrig,ROTATE_DEGREES,0..360)
>
>wait(1)
>run!
>execute!
>```
>
>
>**Arguments:**
>
>| # | name | type | default value | description |
>| - | ---- | ---- | ------------- | ----------- |
>| 1 | `counter` | `@counter` or `@item` | |number (can be a counter or item ID) |
>| 2 | `trig` | `@object` | |Trigger object that will be executed |
>| 3 | `key` | `@object_key` | |Trigger key/value that will be replaced with the counter value |
>| 4 | `range` | `@range` | `0..1024` |range posible value range. if the counter is @counter type, it will take range from its byte |
>| 5 | `multiplier` | `@number` | `1` |value in counter will be multiplied by this number before executed on the trigger|
>
