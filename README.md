# WarEra API — Community Documentation

> **Disclaimer:** This documentation is community-made and is **not affiliated with, endorsed by, or maintained by the WarEra development team**. It was created by exploring the API endpoints and observing response structures. It may be incomplete or out of date. Use at your own discretion.

## What is this?

[WarEra](https://warera.io) is a browser-based strategy game. Its backend exposes a [tRPC](https://trpc.io) API at `https://api2.warera.io/trpc/`.

The official API docs at [api2.warera.io/docs/](https://api2.warera.io/docs/) list available endpoints but do not document response structures. This site fills that gap.

## How to use

Browse endpoints using the sidebar. Each endpoint page documents:

- **Auth** — whether authentication is required or optional
- **Input** — parameters the endpoint accepts
- **Output** — full response structure with field types
- **Notes** — observed quirks and aliases
- **Example request** — a ready-to-use URL

A machine-readable `spec.json` is available alongside each `spec.md` for programmatic use.

## Making requests

WarEra uses tRPC, which maps to HTTP GET requests:

```
GET https://api2.warera.io/trpc/<namespace>.<method>
GET https://api2.warera.io/trpc/<namespace>.<method>?input=<JSON>
```

For authenticated endpoints, include your session token as a Bearer token in the `Authorization` header.

## Contributing

Found an undocumented endpoint or a field that's wrong? PRs are welcome on [GitHub](https://github.com/majimawrks/warera-api-docs). Follow the existing `spec.md` and `spec.json` format in the `specs/` folder.

---

## Support

<div class="support-block">
  <p class="support-desc">If this documentation has been useful to you, consider supporting its development.</p>
  <div class="support-table">
    <div class="support-row">
      <span class="support-label">SAWERIA</span>
      <a class="support-value support-link" href="https://saweria.co/gdsst" target="_blank" rel="noopener">
        saweria.co/gdsst
        <svg class="support-ext-icon" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M2 10L10 2M10 2H4M10 2V8" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </a>
    </div>
    <div class="support-row">
      <span class="support-label">BITCOIN</span>
      <span class="support-value support-addr" data-addr="bc1qp6fh0a00rezpnsec620mcp7myclk74q3grm8mg">bc1qp6fh0a00rezpnsec620mcp7myclk74q3grm8mg</span>
      <button class="support-copy" onclick="supportCopy(this)" data-addr="bc1qp6fh0a00rezpnsec620mcp7myclk74q3grm8mg">COPY</button>
    </div>
    <div class="support-row">
      <span class="support-label">ETHEREUM<br><span class="support-sublabel">MAINNET</span></span>
      <span class="support-value support-addr">0x94c710f78E7086Cb6a75C6cF9362Cb95dF938b7E</span>
      <button class="support-copy" onclick="supportCopy(this)" data-addr="0x94c710f78E7086Cb6a75C6cF9362Cb95dF938b7E">COPY</button>
    </div>
  </div>
</div>
