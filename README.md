# Evri (evri)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Evri is the United Kingdom's largest dedicated parcel delivery company, formerly Hermes UK, headquartered in Leeds and majority owned by Apollo-managed funds. Following the CMA-cleared 2025 merger with DHL eCommerce UK, the combined group delivers more than a billion parcels a year across a courier network of 30,000+ couriers and van drivers, thousands of ParcelShops and lockers, and domestic, returns and international services for retailers and marketplace sellers. Evri sits at the last-mile end of the supply chain — the carrier a shipper, retailer or e-commerce platform hands a parcel to for final delivery in the UK. Its API posture is customer-contract portal only: Evri publishes no developer portal, no public API reference and no machine-readable specification. The host api.evri.com resolves to a live Tyk API Gateway (5.13.0) whose only publicly reachable path is an unauthenticated health check; every other probed path returns 404 and no listen path is discoverable without credentials. Shipment, label, ParcelShop, Print in Store and tracking credentials are issued by an Evri account manager or sales representative to contracted Corporate or Business accounts, with sandbox and production credentials handed over by email. In practice most integrators reach Evri indirectly through shipping-API aggregators such as EasyPost, ShipEngine / ShipStation, Sendcloud, AfterShip and Intersoft Sapient rather than directly.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/evri/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/evri/refs/heads/main/apis.yml)

## Tags

- Logistics
- Supply Chain
- United Kingdom
- Parcel
- Last Mile Delivery
- Courier
- Track and Trace
- Returns
- E-commerce
- Shipping

## Timestamps

- **Created:** 2026-07-30
- **Modified:** 2026-07-30

## APIs

No public APIs are listed. Evri publishes no developer portal, no API reference, and no machine-readable API contract on any first-party host. The API family that exists — shipment and label creation, ParcelShop lookup, Print in Store / QR returns, and tracking — is documented only to contracted Corporate and Business customers, whose credentials are issued by an Evri account manager. Rating is absent entirely: ShipEngine documents that EVRi has no available Rates API and that contracted rates are supplied out of band.

See [`review.yml`](review.yml) for the full probe record and the interoperability assessment.

## Interoperability

- **Standard conformance:** No standard reference found. No DCSA, IATA ONE Record, IATA Cargo-XML, GS1/EPCIS, UN/EDIFACT, ANSI X12, UN/CEFACT, WCO Data Model, eFTI, MLETR/eBL or NMFTA claim. Not a designated postal operator, so no UPU posture.
- **Interface shape:** `proprietary-undocumented` — a production Tyk-managed API estate exists at `api.evri.com`, but no contract is published anywhere public.
- **Identifier scheme:** Vendor-proprietary only — Evri parcel tracking number plus Evri-issued Client ID / Child Client ID account keys. No GS1 SSCC/GTIN/GLN, no UPU S10, no SCAC.
- **Event model:** `none-published`. No webhook, subscription or AsyncAPI documentation. The only evidenced delivery mechanism is batch — SFTP tracking data files and CSV bulk upload. Webhooks that developers experience as "Evri webhooks" are manufactured by the aggregator layer.
- **EDI legacy:** No EDI referenced. No EDIFACT, X12, VAN or AS2. The batch path is flat file over SFTP, not EDI.
- **Multi-party posture:** Publishes to contracted counterparties only, and mostly by proxy through EasyPost, ShipEngine/ShipStation, Sendcloud, AfterShip, Intersoft Sapient and Despatch Cloud. Evri's own published integration directory is a set of marketplace connectors (eBay, Amazon, Etsy, Shopify, WooCommerce, Magento, BigCommerce, Squarespace, OnBuy, TikTok Shop, Temu, Not On The High Street) that terminate in Evri's own dashboard, not in the customer's stack.
- **Access gate:** `commercial-agreement`. An Evri Corporate or Business account first, then an email to the account manager or sales representative, who issues sandbox and production credentials. Nothing self-serve, no published API terms, no published rate limits.

## Common Properties

- [Website](https://www.evri.com/)
- [Business Portal](https://business.evri.com/) — authenticated customer login, not a developer portal
- [Help Centre](https://www.evri.com/help-and-support/help-centre)
- [Business Accounts](https://www.evri.com/business-accounts)
- [Bulk Send Marketplace Connectors](https://www.evri.com/our-services/bulk-send)
- [International Send](https://www.evri.com/international-send)
- [Responsible Disclosure Policy](https://www.evri.com/responsible-disclosure-policy)
- [Cyber Security](https://www.evri.com/cyber-security)
- [Service Status](https://www.evri.com/service-status)
- [Track a Parcel](https://www.evri.com/track-a-parcel)
- [About Us](https://www.evri.com/about-us)
- [Leadership](https://www.evri.com/leadership)
- [Annual Reports](https://www.evri.com/annual-reports)
- [Press](https://www.evri.com/press)

## Maintainers

- Kin Lane — kin@apievangelist.com
