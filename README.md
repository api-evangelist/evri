# Evri (evri)

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
