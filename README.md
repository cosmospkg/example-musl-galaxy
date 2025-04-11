# 🌌 Cosmos Example Galaxy

> A minimal Galaxy for Cosmos used to demonstrate local and offline installation flows.

This repository contains a basic working Galaxy with a small, statically linked `hello` binary and a sample Nebula (`core-stack`) to show how a Cosmos install flow works.

---

## 📦 Included Stars

- `hello` – statically linked binary, installs to `/usr/bin/hello`
- `core-stack` – a Nebula that depends on `hello`, simulates a base install stack

---

## 📂 Layout

```txt
example-galaxy/
├── meta.toml
├── stars/
│   ├── hello.toml
│   └── core-stack.toml
├── packages/
│   └── hello-0.1.0.tar.gz
```

---

## 🚀 Quick Usage

1. Add this Galaxy to your `config.toml`:

```toml
[galaxies]
example = "file:///path/to/example-galaxy"
```

2. Run a test install:

```bash
cosmos install core-stack --root ./test-root
```

3. Inspect:

```bash
ls ./test-root/usr/bin
./test-root/usr/bin/hello
```

Run it if you’re brave:
```bash
chroot ./test-root /usr/bin/hello
```

---

## 🤖 What This Galaxy Is
- A working example of a local/offline Cosmos Galaxy
- A reference for Galaxy structure and metadata layout
- A testable install target for Stellar-built packages

---

## 🧠 What This Galaxy Is Not
- Secure
- Signed
- Maintained for long-term use
- A full Linux base system (see [LFS Galaxy](https://github.com/cosmospkg/lfs-galaxy-mirror))

---

## 🧰 Dev Notes

To build a new package:

```bash
stellar new-star mypkg
# edit star.toml and files/
stellar build-star ./mypkg
# move the .tar.gz to packages/ and star.toml to stars/
```

Then update `meta.toml` to include the new Star and version.

---

## 🔗 Links
- [Cosmos CLI & Core](https://github.com/cosmospkg/cosmos)  
- [Stellar Package Builder](https://github.com/cosmospkg/cosmos/tree/main/stellar)  
- [Documentation](https://docs.cosmos-pkg.org)

---

> If you can install this, you can install the world.

