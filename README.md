# KV &emsp; [![Latest Version]][crates.io] ![Build Status] ![Quality Checks] ![License Checks] ![Security Checks] [![Code Coverage]][codecov.io]

[Build Status]: https://github.com/wayfair-tremor/kv/workflows/Tests/badge.svg
[Quality Checks]: https://github.com/wayfair-tremor/kv/workflows/Checks/badge.svg
[License Checks]: https://github.com/wayfair-tremor/kv/workflows/License%20audit/badge.svg
[Security Checks]: https://github.com/wayfair-tremor/kv/workflows/Security%20audit/badge.svg
[Code Coverage]: https://codecov.io/gh/wayfair-tremor/kv/branch/main/graph/badge.svg
[codecov.io]: https://codecov.io/gh/wayfair-tremor/kv
[Latest Version]: https://img.shields.io/crates/v/tremor-kv.svg
[crates.io]: https://crates.io/crates/tremor-kv

**kv parser**

---

KV parsing inspired by logstash's kv plugin.

Parses a string into a map. It is possible to split based on different characters that represent
either field or key value boundaries.

A good part of the logstash functionality will be handled outside of this function and in a
generic way in tremor script.

## Use as a library

The kv parser was designed so that KV style parsing could be embedded into [tremor](https://www.tremor.rs)'s [scripting](https://docs.tremor.rs/tremor-script/) language for [extract](https://docs.tremor.rs/tremor-script/extractors/kv/) operations.

The parser can also be used standalone

```rust
  let kv = Pattern::compile("%{key}%{%{val}").expect("Failed to build pattern");
  let r = kv.run("this%{is a%{test").expect("Failed to split input");
  assert_eq!(r.len(), 2);
  assert_eq!(r["this"], "is");
  assert_eq!(r["a"], "test");
```

