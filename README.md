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

#### Contains `contains($list, $value)`

Returns _true_ if the `$value` is present in the `$list`. Uses `index` internally.

```scss
contains( (1, 2, 3), 2 );
=> true
```

## License

This project is provided under the terms of the [MIT License](LICENSE.md).

---

Authored by **James Kyle** · [Github](https://github.com/thejameskyle) · [Twitter](https://twitter.com/thejameskyle) · [CodePen](https://codepen.com/thejameskyle)

[Built Equal](www.hrc.org/donate) · [Made in Boston](http://bostonbuilt.org/)
