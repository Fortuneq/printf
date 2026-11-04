### sprintf and sscanf

- int sscanf(const char *str, const char *format, ...) - reads formatted input from a string.
- int sprintf(char *str, const char *format, ...) - sends formatted output to the string pointed to by str.

where:
- str − the C string the function processes as the source for retrieving data;
- format − a C string containing one or more of the following items: a whitespace character, a non-whitespace character and format specifiers. A format specifier for printing functions follows the prototype: %[flags][width][.precision][length]specifier. A format specifier for scanning functions follows the prototype: %[*][width][length]specifier.

### sprintf and sscanf Specifiers

| No. | Specifier | sprintf output | sscanf output |
| --- | --- | --- | --- |
| 1 | c | Character | Character |
| 2 | d | Signed decimal integer | Signed decimal integer |
| 3 | i | Signed decimal integer | Signed integer (may be decimal, octal or hexadecimal) |
| 4 | e | Scientific notation (mantissa/exponent) using e (output must match with precision up to e-6) | Decimal floating-point number or scientific notation (mantissa/exponent) |
| 5 | E | Scientific notation (mantissa/exponent) using E | Decimal floating-point number or scientific notation (mantissa/exponent) |
| 6 | f | Decimal floating-point number | Decimal floating-point number or scientific notation (mantissa/exponent) |
| 7 | g | Uses the shortest representation of the decimal number | Decimal floating-point number or scientific notation (mantissa/exponent) |
| 8 | G | Uses the shortest representation of the decimal number | Decimal floating-point number or scientific notation (mantissa/exponent) |
| 9 | o | Unsigned octal | Unsigned octal |
| 10 | s | String of characters | String of characters |
| 11 | u | Unsigned decimal integer | Unsigned decimal integer |
| 12 | x | Unsigned hexadecimal integer | Unsigned hexadecimal integer (any letters) |
| 13 | X | Unsigned hexadecimal integer (uppercase letters) | Unsigned hexadecimal integer (any letters) |
| 14 | p | Pointer address | Pointer address |
| 15 | n | Number of characters printed before %n | Number of characters read before %n |
| 16 | % | The % character | The % character |

### sprintf Flags

| No. | Flag | Description |
| --- | --- | --- |
| 1 | - | Left-justify within the given field width; right justification is the default (see the width sub-specifier). |
| 2 | + | Forces the result to be preceded by a plus or minus sign (+ or -) even for positive numbers. By default only negative numbers are preceded by a "-" sign. |
| 3 | (space) | If no sign is going to be written, a blank space is inserted before the value. |
| 4 | # | Used with o, x or X specifiers, the value is preceded by 0, 0x or 0X respectively (for values other than zero). Used with e, E and f, it forces the written output to contain a decimal point even if no digits follow. By default, if no digits follow, no decimal point is written. Used with g or G, the result is the same as with e or E, but trailing zeros are not removed. |
| 5 | 0 | Left-pads the number with zeros (0) instead of spaces where padding is specified (see the width sub-specifier). |

### sprintf and sscanf Width

| No. | Width | Description |
| --- | --- | --- |
| 1	| (number) | Minimum number of characters to be printed. If the value to be printed is shorter than this number, the result is padded with blank spaces. The value is not truncated even if the result is larger. |
| 2 | * | In sprintf, * means the width is not specified in the format string but as an additional integer argument preceding the argument that has to be formatted. In sscanf, a * placed after % and before the format specifier reads data of the specified type but suppresses its assignment. |

### sprintf Precision

| No. | .precision | Description |
| --- | --- | --- |
| 1	| .number | For integer specifiers (d, i, o, u, x, X), precision specifies the minimum number of digits to be written. If the value to be written is shorter than this number, the result is padded with leading zeros. The value is not truncated even if the result is longer. A precision of 0 means that no character is written for the value 0. For e, E and f specifiers it is the number of digits to be printed after the decimal point. For g and G specifiers it is the maximum number of significant digits to be printed. For s it is the maximum number of characters to be printed; by default all characters are printed until the terminating null character is encountered. For c it has no effect. If no precision is specified for e, E, f, g and G, the default is 6. If no precision is specified for the other specifiers, the default is 1. If the period is given without an explicit value, the default is 0. |
| 2	| .* | The precision is not specified in the format string but as an additional integer argument preceding the argument that has to be formatted. |

### sprintf and sscanf Length

| No. | Length | Description |
| --- | --- | --- |
| 1 | h | The argument is interpreted as a short int or unsigned short int (only applies to integer specifiers: i, d, o, u, x and X). |
| 2 | l | The argument is interpreted as a long int or unsigned long int for integer specifiers (i, d, o, u, x and X), and as a wide character or wide character string for specifiers c and s. |
| 3 | L | The argument is interpreted as a long double (only applies to floating-point specifiers − e, E, f, g and G). |

### Special string processing functions (inspired by the String class in C#)

| No. | Function | Description |
| ------ | ------ | ------ |
| 1 | void *to_upper(const char *str) | Returns a copy of string (str) converted to uppercase. In case of any error, return NULL |
| 2 | void *to_lower(const char *str) | Returns a copy of string (str) converted to lowercase. In case of any error, return NULL |
| 3 | void *insert(const char *src, const char *str, size_t start_index) | Returns a new string in which a specified string (str) is inserted at a specified index position (start_index) in the given string (src). In case of any error, return NULL |
| 4 | void *trim(const char *src, const char *trim_chars) | Returns a new string in which all leading and trailing occurrences of a set of specified characters (trim_chars) from the given string (src) are removed. In case of any error, return NULL |
