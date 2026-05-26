# mce-proc - Markdown Code Extractor procedural macros

See and use Markdown Code Extractor [`prudent/mce`](https://github.com/prudent-rs/mce).

## Other details

### Configuration in TOML only

See [`prudent/mce` -> `README.md`](https://github.com/prudent-rs/mce/blob/main/README.md)
for why configuration is in TOML only.

### `nth***` and `mce_tag***` extractions do repeat parsing

Every invocation of `nth***` and `mce_tag***` extraction macros do parse the whole file (`README.md`
or as configured). The cost is irrelevant, and for must use cases negligible. We do NOT cache/store
any data/content between the macro invocations. Why? Rust macros must not keep/depend on any state
between their invocations.
