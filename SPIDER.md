# Spider build of V8 for rusty_v8 v152.2.0

Built from tag v152.2.0, commit 2768994f664e8a6e3aba27503606c58339136e2a.
Built commit on this branch: 1db18c238a76e4d0e42b4e5d803d29667a9c06fc (tag + v8 submodule move + spider-build.yml).

## Step 2: tag vs crates.io
- Cargo.toml version: 152.2.0.
- crates.io v8 152.2.0 (fetched with cargo) vs the tag: build.rs identical; src/ (66 entries: Rust files and binding.cc) identical (`diff -rq`, no differences).

## V8 / ICU
- v8 submodule moved to cb19e120a39e71aef139dc333a2e6a5d46635ede (denoland/v8 15.2-lkgr-denoland); include/v8-version.h: 15.2.124.45.
- ICU left as in the tag (d578f2e8b7bd5938e21cfb6bf15c079e0aa5b738); V8's DEPS at that commit names the same revision.
- No other change to V8 and none to the crate's Rust or C++ code.

## Targets
Run: https://github.com/spider-dev-ai/rusty_v8/actions/runs/43487692511

### x86_64-unknown-linux-gnu: built (release; fmt, tests, clippy passed)
- Artifact: spider_release_x86_64-unknown-linux-gnu, id 14073700942
- librusty_v8_release_x86_64-unknown-linux-gnu.a.gz SHA-256: f2c1d1e7e99879bbec665dda40fc77ea8164518236859280e3e2d9d6450bc0af
- src_binding_release_x86_64-unknown-linux-gnu.rs SHA-256: 60ab61fcbb92983670f6d7187b284a8480a8a69f0f4229eb4236fb6f1191d2e0
- V8 version: 15.2.124.45
- Hashes recomputed locally from the downloaded artifact; they match the run's checksums file.

### aarch64-apple-darwin: not built
- Attempt 1 (job 132100389127): cancelled with no steps, 18:58 to 19:13 UTC.
- Attempt 2, the single re-run (job 132147496682): cancelled with no steps, 20:24 to 20:39 UTC.
- Not re-run a third time, as instructed.
