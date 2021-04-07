

# A light weight  runtime for ReScript.

The motiviation of this repo is that when ReScript users want to 
share their library with JS users, the JS users don't need have 
ReScript toolchain installed, this makes sharing code with JS users easier.

It shares the same version schema with ReScript compiler.

When you use this library, the config would be adding such things in bsconfig.json

```json
"external-stdlib" : "@rescript/std"
```
