
A `generator` in [[Python]] is a [[Python/Functions|function]] or expression that returns a special type of [iterator](https://docs.python.org/3.11/glossary.html#term-iterator) called [generator iterator](https://docs.python.org/3.11/glossary.html#term-generator-iterator). `Generator-iterators` are [lazy](https://en.wikipedia.org/wiki/Lazy_evaluation): they do not store their `values` in memory, but _generate_ their values when needed.

A generator function looks like any other function, but contains one or more [yield expressions](https://docs.python.org/3.11/reference/expressions.html#yield-expressions). Each `yield` will suspend code execution, saving the current execution state (_including all local variables and try-statements_). When the generator resumes, it picks up state from the suspension - unlike regular functions which reset with every call.

