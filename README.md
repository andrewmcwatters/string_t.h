# string_t.h
A code snippet for C strings with length

## SYNOPSIS
```C
#include "string_t.h"
```

## DESCRIPTION
The _"string_t.h"_ header shall define **string_t**.

### `string_t`
```C
struct string_t {
    size_t  cap;
    size_t  len;
    char   *str;
};
```

## EXAMPLES

**Copying and freeing a string_t**
```C
const char *cs;
struct string_t *s;

cs = foo();
s = (struct string_t *)malloc(sizeof string_t);
s->len = s->cap = strlen(cs) + 1;
s->str = strdup(cs);
free(s->str);
free(s);
```

## Questions
* Can you make `string_t` compatible with `std::string` long string mode?
* Would it be preferrable to expose C wrappers to `std::string` if one is going
to use the same underlying struct layout?

## Further reading
\[1]: https://en.wikipedia.org/wiki/String_(computer_science)#Length-prefixed  
\[2]: http://www.catb.org/esr/structure-packing/  
\[3]: https://joellaity.com/2020/01/31/string.html  
\[4]: https://stackoverflow.com/questions/21694302/what-are-the-mechanics-of-short-string-optimization-in-libc  
\[5]: https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/string.h.html

## License
GNU General Public License v2.0
