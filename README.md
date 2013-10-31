Ballistic [![Build Status](https://travis-ci.org/tctcl/ballistic.png?branch=master)](https://travis-ci.org/tctcl/ballistic) [![Dependency Status](https://david-dm.org/tctcl/ballistic.png)](https://david-dm.org/tctcl/ballistic) [![devDependency Status](https://david-dm.org/tctcl/ballistic/dev-status.png)](https://david-dm.org/tctcl/ballistic#info=devDependencies)
========

Powerful Function Library for Sass

## Lists

#### Compact `compact($list)`

Returns a copy of the list with all falsy values removed.

```scss
compact( (0, 1, false, 2, '', 3 ) );
=> (1, 2, 3)
```

#### Contains `contains($list, $value)` _Alias:_ **include**

Returns _true_ if the `$value` is present in the `$list`. Uses `index` internally.

```scss
contains( (1, 2, 3), 2 );
=> true
```

#### First `first($list, [$n])` _Alias:_ **head**, **take**

Returns the first element of a `$list`. Passing `$n` will return the first `$n` elements of the `$list`.

```scss
first( (5, 4, 3, 2, 1) );
=> 5
```

#### Flatten `flatten($list, [$shallow])`

Flattens a nested `$list` (the nesting can be to any depth). If you pass `$shallow`, the `$list` will only be flattened a single level.

```scss
flatten( (1, (2), (3, ((4)))) );
=> (1, 2, 3, 4);

flatten( (1, (2), (3, ((4)))), true );
=> (1, 2, 3, ((4)));
```

#### Initial `initial($list, [$n])`

Returns everything but the last entry of the `$list`. Pass `$n` to exclude the last `$n` elements from the result.

```scss
initial( (5, 4, 3, 2, 1) );
=> (5, 4, 3, 2)
```

#### Intersection `intersection($lists...)`

Computes the list of values that are the intersection of all the `$lists`. Each value in the result is present in each of the `$lists`.

```scss
intersection( (1, 2, 3), (101, 2, 1, 10), (2, 1) );
=> (1, 2)
```

#### Last `last($list, [$n])`

Returns the last element of an `$list`. Passing `$n` will return the last `$n` elements of the `$list`.

```scss
last( (5, 4, 3, 2, 1) );
=> 1
```

#### Prepend `prepend($list, $item)`

Prepends a single `$item` onto the start of a `$list`.

```scss
prepend( (2, 3, 4), 1 );
=> (1, 2, 3, 4)
```

#### Rest `rest($list, [$n])` _Alias:_ **tail**, **drop**

Returns the rest of the elements in an `$list`. Passing `$n` will return the values of the `$list` from `$n` onward.

```scss
rest( (5, 4, 3, 2, 1) );
=> (4, 3, 2, 1)
```

#### Slice `slice($list, [$min], [$max])`

Returns a copy of the list between `$min` and `$max`. `$min` defaults to the start of the list, `$max` defaults to the end of the list. Negative values are valid and will count from the end of the list.

```scss
slice( (1, 2, 3, 4, 5), 2, 4 )
=> (2, 3, 4)
```

#### Union `union($lists...)`

Computes the union of the passed-in `$lists`: the list of unique items, in order, that are present in one or more of the `$lists`.

```scss
union( (1, 2, 3), (101, 2, 1, 10), (2, 1));
=> (1, 2, 3, 101, 10)
```

#### Without `without($list, [$values...])`

Returns a copy of the `$list` with all instances of the `$values` removed.

```scss
without( (1, 2, 1, 0, 3, 1, 4), 0, 1 );
=> (2, 3, 4)
```

## Numbers

#### Absolute Unit `absolute-unit($number)`

Returns _true_ if the `$number` is an absolute value.

```scss
absolute-unit(10px);
=> true
```

#### Ceil To `ceil-to($number, $precision)`

Returns `$number` rounded up to the `$precision` decimal place.

```scss
ceil-to( 0.1234, 2 );
=> 0.13
```

#### Convert `convert($number, $unit, [$ref])`

Returns `$number` converted to `$unit`. Relative Units require a `$ref`. Valid `$unit`s are `px`, `pc`, `pt`, `in`, `cm`, `mm`, `em*`, `rem*`, `ex*`, `ch*`, `ms`, `s`, `deg`, `grad`, `rad`, and `turn`. *needs `$ref`.

```scss
convert(10px, "in");
=> 0.104166667in
convert(10px, "em", 10);
=> 1em
```

#### E `e()`

Returns Euler's Number.

```scss
e();
=> 2.71828182845
```

#### Exponent `exponent($number, $exponent)` _Alias:_ **power**, **pow**

Returns `$number` multiplied exponentially to `$exponent`.

```scss
exponent(2, 2);
=> 4
```

#### Factorial `factorial($number)` _Alias:_ **fact**

Returns the factorial of `$number`.

```scss
factorial(3);
=> 6
```

#### Floor To `floor-to($number, $precision)`

Returns `$number` rounded down to the `$precision` decimal place.

```scss
floor-to( 0.1234, 2 );
=> 0.12
```

#### Infinity `infinity()`

Returns sass infinity.

```scss
infinity();
=> 1/0
```

#### Is Unit `is-unit($number, $unit)`

Returns true if `$number` is `$unit`.

```scss
is-unit(1px, "px");
=> true
```

#### Limit `limit($number, [$min], [$max])`

Returns `$number` rounded to be between `$min` and `$max`. 

```scss
limit(3, 10, 20);
=> 10
```

#### Parse Int `parse-int($number)`

Returns copy of `$number` without any unit.

```scss
parse-int(10px);
=> 10
```

#### Phi `phi()` _Alias:_ **golden-ratio**

Returns Phi.

```scss
phi();
=> 1.61803398874
```

#### Pi `pi()`

Returns Pi.

```scss
pi();
=> 3.14159265359
```

#### Relative Unit `relative-unit($number)`

Returns _true_ if the `$number` is an relative value.

```scss
relative-unit(10em);
=> true
```

#### Round To `round-to($number, $precision)`

Returns `$number` rounded to the `$precision` decimal place.

```scss
round-to( 0.1234, 2 );
=> 0.12
```

#### Tau `tau()`

Returns Tau.

```scss
tau();
=> 6.2831853072
```

#### Unit Type `unit-type($number)`

Returns unit type of `$number` (relative, absolute, or unitless).

```scss
unit-type(1em);
=> "relative"
```

## License

This project is provided under the terms of the [MIT License](LICENSE.md).

---

Authored by **James Kyle** · [Github](https://github.com/thejameskyle) · [Twitter](https://twitter.com/thejameskyle) · [CodePen](https://codepen.com/thejameskyle)

[Built Equal](www.hrc.org/donate) · [Made in Boston](http://bostonbuilt.org/)
