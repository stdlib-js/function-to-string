<!--

@license Apache-2.0

Copyright (c) 2022 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# function2string

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return a string representing the source code of a provided function.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

To use in Observable,

```javascript
function2string = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/function-to-string@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var function2string = require( 'path/to/vendor/umd/function-to-string/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/function-to-string@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.function2string;
})();
</script>
```

#### function2string( fcn )

Returns a string representing the source code of a provided function.

```javascript
function add( x, y ) {
    return x + y;
}

var str = function2string( add );
// e.g., returns 'function add( x, y ) {\n    return x + y;\n}'
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   If called on built-in functions, functions created by `Function.prototype.bind()`, or other non-JavaScript functions, the function returns a "native" function string similar to the following:

    ```text
    "function foo() { [native code] }"
    ```

    For intrinsic object methods and functions, `foo` is the initial name of the function.

-   If called on a function created by the [`Function`][@stdlib/function/ctor] constructor, the function returns the source code of a synthesized function declaration having the name "anonymous" and using the provided parameters and function body.

-   Starting in ES2018, the ECMAScript specification requires that the returned string contain the exact same source code as it was declared, including any whitespace and/or comments. If the host is unable to access the source code, the specification requires that the returned string be the native function string.  

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-ctor@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-erf@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/blas-base-daxpy@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/string-kebabcase@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/random-base-randu@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/string-format@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/function-to-string@umd/browser.js"></script>
<script type="text/javascript">
(function () {

var fcns = [
    [ 'ndarray', ndarray ],
    [ 'erf', erf ],
    [ 'daxpy', daxpy ],
    [ 'kebabcase', kebabcase ],
    [ 'randu', randu ],
    [ 'format', format ],
    [ 'function2string', function2string ]
];

var i;
for ( i = 0; i < fcns.length; i++ ) {
    console.log( format( 'Function: %s\n\n%s\n', fcns[ i ][ 0 ], function2string( fcns[ i ][ 1 ] ) ) );
}

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/function-ctor`][@stdlib/function/ctor]</span><span class="delimiter">: </span><span class="description">function constructor.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/function-to-string.svg
[npm-url]: https://npmjs.org/package/@stdlib/function-to-string

[test-image]: https://github.com/stdlib-js/function-to-string/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/function-to-string/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/function-to-string/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/function-to-string?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/function-to-string.svg
[dependencies-url]: https://david-dm.org/stdlib-js/function-to-string/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/function-to-string/tree/deno
[deno-readme]: https://github.com/stdlib-js/function-to-string/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/function-to-string/tree/umd
[umd-readme]: https://github.com/stdlib-js/function-to-string/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/function-to-string/tree/esm
[esm-readme]: https://github.com/stdlib-js/function-to-string/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/function-to-string/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/function-to-string/main/LICENSE

[@stdlib/function/ctor]: https://github.com/stdlib-js/function-ctor/tree/umd

<!-- <related-links> -->

<!-- </related-links> -->

</section>

<!-- /.links -->
