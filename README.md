# Documentation for `toConstOpti`

_Generated using `spwn doc [file name]` with some revision_

## Info

- Uses 0 groups
- Uses 0 colors
- Uses 0 block IDs
- Uses 1 item IDs

- Adds 0 objects

## Exports

```spwn
{
    toConstOpti: ( /* ... */ ) { /* ... */ }
}
```

**Type:** `@dictionary`

## Macros

### toConstOpti

>
>```spwn
>toConstOpti = (
>   counter     : (@counter | @item),
>   trig        : @object,
>   key         : @object_key,
>   range       : @range        = 0..1024,
>   modifier    : @macro        = n=>n
> ){ /* ... */ }
>```
>
>**Type:** `@macro`
>
>**Example:**
>
>```spwn
>number = counter(1i)
>rotateTrig = rotate_trigger(100g,101g,0,2)
>execute = toConstOpti(number,rotateTrig,ROTATE_DEGREES)
>
>alphaTrig = alpha_trigger(1g,0,0.5)
>run = toConstOpti(2i, alphaTrig, OPACITY, 0..100, n=>n*0.01)
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
>| 5 | `modifier` | `@macro` | `n=>n` | Value on counter will be processed through this macro before placed on the trigger. |
>