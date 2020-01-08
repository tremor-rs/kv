# KV &emsp; ![Build Status] ![Quality Checks] ![License Checks] ![Security Checks] [![Code Coverage]][codecov.io]

[Build Status]: https://github.com/wayfair-incubator/kv/workflows/Tests/badge.svg
[Quality Checks]: https://github.com/wayfair-incubator/kv/workflows/Checks/badge.svg
[License Checks]: https://github.com/wayfair-incubator/kv/workflows/License%20audit/badge.svg
[Security Checks]: https://github.com/wayfair-incubator/kv/workflows/Security%20audit/badge.svg
[Code Coverage]: https://codecov.io/gh/wayfair-incubator/kv/branch/master/graph/badge.svg
[codecov.io]: https://codecov.io/gh/wayfair-incubator/kv

**kv parser**

---

KV parsing inspired by logstash's kv plugin.

Parses a string into a map. It is possible to split based on different characters that represent
either field or key value boundaries.

A good part of the logstash functionality will be handled outside of this function and in a
generic way in tremor script.
