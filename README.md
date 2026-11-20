# lib-archive

`archive` — Handl stdlib port (pure handl).

## Layout

```text
src/index.hnl            the library (pure handl)
pkg.hnl                  package manifest
scripts/hnl-gate.sh      the gate
```

## Gate

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.
