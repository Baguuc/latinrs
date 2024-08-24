# Latin.rs

Latin.rs is a package that transliterates text and characters into thier latin form.

# Data

The data is not mine, I got it from python [translitcodec](https://github.com/claudep/translitcodec/tree/master) package, to be explicit it is the "long_table" from [this](https://github.com/claudep/translitcodec/blob/master/translitcodec/__init__.py) file.

# Usage

To encode a **string** into its latin form you can use _encode_str_ function,
it will return a str with all characters encoded with their latin form
Example:

```rust
let s = "Zażółć gęślą jaźń EUR :-)?!@#";
let latin = latinrs::encode_char(s);

assert_eq!("Zazolc gesla jazn EUR :-)?!@#".to_string(), latin);

let s = "Hello, World!";
let latin = latinrs::encode_str(s);

assert_eq!("Hello, World!".to_string(), latin);
```

To encode a **single character** into its latin form you can use _encode_char_ function,
if the provided character is not special it will be returned in it's original form.
Note that the output of this function is str meaning **it can be longer than one character**.
Example:

```rust
let chr = 'Ż';
let latin = latinrs::encode_char(chr);

assert_eq!("Z".to_string(), latin);


let chr = 'a';
let latin = latinrs::encode_char(chr);

assert_eq!("a".to_string(), latin);


let chr = '␐';
let latin = latinrs::encode_char(chr);

assert_eq!("DLE".to_string(), latin);
```
