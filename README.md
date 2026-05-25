# mce-proc - Markdown Code Extractor procedural macros

See and use Markdown Code Extractor [`prudent/mce`](https://github.com/prudent-rs/mce).

## Other details

### TOML only

See [`prudent/mce-lib` -> `README.md`](https://github.com/prudent-rs/mce-lib/blob/main/README.md)
for why we use TOML only.

### `nth***` and `mce_tag***` extractions do repeat parsing

Every invocation of `nth***` and `mce_tag***` extraction macros do parse the whole file (`README.md`
or as configured). The cost is irrelevant, and for must use cases negligible. We do NOT cache/store
any data between the macro invocations. Why? Rust macros must not keep/depend on any state between
their invocations.
