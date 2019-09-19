Statically linking with `libc++` results in the following error:

Note before running `cargo build` make sure to adapt the library search path `/Users/bas/Engineering/sigill-error` in `.cargo/config` to the absolute working directory.

```
cargo build
   Compiling sigill-error v0.0.0 (/Users/bas/Engineering/sigill-error)
error: Could not compile `sigill-error`.

Caused by:
  process didn't exit successfully:
  `rustc \
    --edition=2018 \
    --crate-name main \
    src/main.rs \
    --color always \
    --crate-type bin \
    --emit=dep-info,link \
    -C debuginfo=2 \
    -C metadata=de7540297549362f \
    -C extra-filename=-de7540297549362f \
    --out-dir /Users/bas/Engineering/sigill-error/target/debug/deps \
    -C incremental=/Users/bas/Engineering/sigill-error/target/debug/incremental \
    -L dependency=/Users/bas/Engineering/sigill-error/target/debug/deps \
    --extern failure=/Users/bas/Engineering/sigill-error/target/debug/deps/libfailure-ae5878520d09736b.rlib \
    --extern serde_derive=/Users/bas/Engineering/sigill-error/target/debug/deps/libserde_derive-5ba0a3c0677ee353.dylib \
    -L /Users/bas/Engineering/sigill-error \
    -lstatic=c++ \
    -lstatic=c++abi \
    -L native=/Users/bas/Engineering/sigill-error/target/debug/build/backtrace-sys-c6d2b18124b0c6e8/out`
    (signal: 4, SIGILL: illegal instruction)
```
