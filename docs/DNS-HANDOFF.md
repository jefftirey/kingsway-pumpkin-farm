# DNS handoff — kingswaypumpkinfarm.com → Vercel

**For:** Jim
**From:** Jeff Tirey
**Date:** 2026-09-03

The new site is live on Vercel. To make kingswaypumpkinfarm.com show it, two DNS records need to change.

## Where the DNS lives today

| | |
|---|---|
| Registrar | IONOS (domain expires 2027-08-21) |
| Nameservers | ns1.siteground.net / ns2.siteground.net |
| Current A record | 35.209.89.159 (SiteGround, the old hacked host) |

Because the nameservers point at SiteGround, the records are edited in the **SiteGround DNS Zone Editor**, not at IONOS. (If you'd rather leave SiteGround entirely, change the nameservers at IONOS instead — see Option B.)

## Option A (recommended): edit two records at SiteGround

In SiteGround → Site Tools → Domain → DNS Zone Editor:

| Type | Name / Host | Value | TTL |
|---|---|---|---|
| A | `@` (root) | `76.76.21.21` | default |
| CNAME | `www` | `cname.vercel-dns.com` | default |

1. **Delete** the existing A record for `@` pointing to 35.209.89.159 and add the new one above.
2. **Delete** any existing A or CNAME for `www` and add the CNAME above.
3. Leave MX / TXT records alone (email is unaffected).

Propagation is usually minutes, up to a few hours. Vercel issues the SSL certificate automatically once it sees the records.

## Option B: move DNS off SiteGround entirely

At IONOS, change the domain's nameservers to:

```
ns1.vercel-dns.com
ns2.vercel-dns.com
```

Then Vercel manages all records. **Only do this if there are no MX/email records on the domain that would need re-creating** — Option A is safer.

## Verify

```bash
dig +short kingswaypumpkinfarm.com A        # expect 76.76.21.21
dig +short www.kingswaypumpkinfarm.com CNAME  # expect cname.vercel-dns.com.
```

Or just open https://kingswaypumpkinfarm.com — Vercel's dashboard will flip the domain from "Invalid Configuration" to "Valid" when it's done.

## After DNS is switched

- Cancel or scrub the SiteGround hosting (it was compromised). Don't just leave it running.
- Change the IONOS and SiteGround passwords, enable 2FA.
