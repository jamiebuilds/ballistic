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

## License

This project is provided under the terms of the [MIT License](LICENSE.md).

---

Authored by **James Kyle** · [Github](https://github.com/thejameskyle) · [Twitter](https://twitter.com/thejameskyle) · [CodePen](https://codepen.com/thejameskyle)

[Built Equal](www.hrc.org/donate) · [Made in Boston](http://bostonbuilt.org/)
