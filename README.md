[![PyPI version](https://img.shields.io/pypi/v/RegexOrder.svg)](https://pypi.python.org/pypi/RegexOrder/)
[![PyPI pyversions](https://img.shields.io/pypi/pyversions/RegexOrder.svg)](https://pypi.python.org/pypi/RegexOrder/)
[![PyPI license](https://img.shields.io/pypi/l/RegexOrder.svg)](https://pypi.python.org/pypi/RegexOrder/)

Search the regex that fits all querying strings.

- Dozens of pre-written regexes are indexed and organized as a [partial order](https://en.wikipedia.org/wiki/Partially_ordered_set), available in `regexorder/templates.json`.

- The regex of all the querying strings' least upper bound in the partial order is returned.

- `templates.svg` plots the partial order.

![Templates](https://raw.githubusercontent.com/chuanconggao/RegexOrder/master/templates.svg?sanitize=true)

The core part is the pre-written regexes and their respective structure. Currently they only cover the most common cases.

- Any idea or contribution is highly welcome.

Our regexes utilize some advanced Unicode features, that are not available in standard `re` library yet. Thus, the more advanced [`regex`](https://pypi.org/project/regex/) library must be used to match our regexes.

## Installation

This package is available on PyPI. Just use `pip3 install -U RegexOrder` to install it.

## Examples

``` python
from regexorder import RegexOrder

r = RegexOrder()

t = r.match("123")
t.name
# 'positive_integer'
t.regex
# '\\+?\\d+'

t = r.matchall(["apple", "banana", "cheese cake"])
t.name
# 'multiple_lowercase_words'
t.regex
# '\\p{Ll}+(\\s+\\p{Ll}+)*'
```
