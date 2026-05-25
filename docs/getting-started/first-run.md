# First Run

After installation, verify the platform starts correctly.

---

## Start ERP Plus

```bash
bin/dev
```

---

## Verify Application

Open:

```txt
http://localhost:3000
```

Verify:

- application loads
- assets compile correctly
- database connection works
- authentication pages render

---

## Verify Test Suite

Run:

```bash
bundle exec rspec
```

Verify:

- tests execute successfully
- no configuration errors exist

---

## Verify Code Quality

Run:

```bash
bundle exec rubocop
```

---

## Next Step

Continue with:

→ [System Overview](../system/index.md)
