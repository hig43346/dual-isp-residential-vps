# Dual ISP residential VPS: what it fixes, why ports 80 and 443 stay closed, and which SixTnet plan to buy

SixTnet's residential entry point is **$25/month** for 2 cores, 2 GB RAM, 40 GB NVMe and 5 TB of traffic, and for most people searching this term that is the right size to start with. Two details decide whether it fits. Ports 80 and 443 are closed on every residential plan, so this is not a web host. And at the time of writing the cart listed 0 available on all four residential tiers, which makes stock the first thing to check, ahead of price.

What follows covers what dual ISP changes about your IP, how SixTnet's two residential lines differ from its standard LAX line, what a year actually costs, and who should buy something else.

> **Quick pick:** Residential-STARTER, $25/month. 2 cores, 2 GB RAM, 5 TB of traffic, one US residential IPv4. Enough for a single TikTok account, a single AI-tool exit, or one streaming region.
> 👉 Check Residential-STARTER pricing and current stock

## SixTnet's full plan list

Prices are USD, taken from the official VPS hosting page and cart page in November 2026. Annual figures are the discounted yearly rate, with the undiscounted list price in brackets.

| Plan | CPU / RAM / NVMe | Network & traffic | Price | Order |
| --- | --- | --- | --- | --- |
| Residential-STARTER | 2 cores / 2 GB / 40 GB | 2 Gbps port, 5 TB/mo, residential IP | $25/mo or $260/yr (list $300) | [Order Residential-STARTER](https://sixtynet.net/aff.php?aff=39) |
| Residential-MICRO | 4 cores / 4 GB / 80 GB | 4 Gbps port, 10 TB/mo, residential IP | $45/mo or $460/yr (list $540) | [Order Residential-MICRO](https://sixtynet.net/aff.php?aff=39) |
| Residential-MEDIUM | 8 cores / 8 GB / 160 GB | 10 Gbps port, 20 TB/mo, residential IP | $85/mo or $860/yr (list $1,020) | [Order Residential-MEDIUM](https://sixtynet.net/aff.php?aff=39) |
| Residential-LARGE | 16 cores / 16 GB / 320 GB | 10 Gbps port, 40 TB/mo, residential IP | $165/mo or $1,660/yr (list $1,980) | [Order Residential-LARGE](https://sixtynet.net/aff.php?aff=39) |
| IRVINE-PRO-STARTER | 2 cores / 2 GB / 40 GB | 2 Gbps port, AS9929, 5 TB/mo, residential IP | $350/yr (list $420) | [Order IRVINE-PRO-STARTER](https://sixtynet.net/aff.php?aff=39) |
| IRVINE-PRO-MICRO | 4 cores / 4 GB / 80 GB | 4 Gbps port, AS9929, 10 TB/mo, residential IP | $550/yr (list $660) | [Order IRVINE-PRO-MICRO](https://sixtynet.net/aff.php?aff=39) |
| LAX-STARTER | 2 cores / 2 GB / 40 GB | 2 Gbps port, 5 TB/mo, DDoS protection | $200/yr (list $240) | [Order LAX-STARTER](https://sixtynet.net/aff.php?aff=39) |
| LAX-MICRO | 4 cores / 4 GB / 80 GB | 4 Gbps port, 10 TB/mo, DDoS protection | $400/yr (list $480) | [Order LAX-MICRO](https://sixtynet.net/aff.php?aff=39) |
| LAX-MEDIUM | 8 cores / 8 GB / 160 GB | 10 Gbps port, 20 TB/mo, DDoS protection | $800/yr (list $960) | [Order LAX-MEDIUM](https://sixtynet.net/aff.php?aff=39) |
| LAX-LARGE | 8 cores / 16 GB / 320 GB | 10 Gbps port, 40 TB/mo, DDoS protection | $1,600/yr (list $1,920) | [Order LAX-LARGE](https://sixtynet.net/aff.php?aff=39) |
| LAX-Storage-500G | 4 cores / 4 GB / 300 GB + 200 GB RAID 10 | 10 Gbps port, 10 TB/mo, DDoS protection | $400/yr (list $480) | [Order LAX-Storage-500G](https://sixtynet.net/aff.php?aff=39) |
| LAX-Storage-1TB | 8 cores / 8 GB / 700 GB + 300 GB RAID 10 | 10 Gbps port, 15 TB/mo, DDoS protection | $700/yr (list $840) | [Order LAX-Storage-1TB](https://sixtynet.net/aff.php?aff=39) |
| Los Angeles China Unicom-Premium | Not listed (network product) | AS9929, 100M base, 3× burst, 95th percentile billing | $2,500/yr (list $3,000) | [Order China Unicom-Premium](https://sixtynet.net/aff.php?aff=39) |

### What the spec sheet leaves out

- **Ports 80 and 443.** Every residential product carries the same notice: closed for IP risk control reasons. The LAX line has no such restriction. This is the difference between a machine that can serve a website and one that cannot.
- **IPv6.** The pricing page doesn't mention it. Two independent reviews of SixTnet's residential line, one from October 2025 and one from July 2026, both report no IPv6 support.
- **IP count.** Each residential VPS comes with a single IPv4, per those same reviews. No extra-IP add-on appears anywhere on the price list, which matters if you run several accounts.
- **IRVINE-PRO access.** The product notes state it rejects all external probes and scans, and that only whitelisted or port-forwarded devices can reach it. Refunds on that line go to account balance only, not back to your payment method.
- **Refund terms generally.** No standard refund window is published on the residential pages. If the ability to walk away matters, get the terms confirmed in a ticket before you pay.
- **Port speed vs throughput.** The 2G/4G/10G figure is the port. A 2025 review of SixTnet's Astound-sourced residential line measured closer to 1 Gbps in practice.

## What "dual ISP residential" is actually doing

An IP address registered to a consumer ISP rather than a hosting provider. IPinfo, MaxMind and IP2Location return `residential` for it instead of `hosting` or `business`, and risk engines treat that tag as a signal. A fresh $5 datacenter VPS routinely fails a TikTok signup, loops on Cloudflare at ChatGPT, and gets "you seem to be using a proxy" from Netflix. Same hardware, different registration, different outcome.

The second meaning of dual ISP is redundancy: two upstream providers so that one failing doesn't take the machine offline. SurferCloud describes its plans that way, and SixTnet's residential products sit in the same category, with the IP registered to a US consumer ISP and the path carried by a partner network.

SixTnet's residential IPs are US-based. What you get in practice is a residential classification in the IP databases, a materially lower fraud score than a datacenter range, cleaner fingerprints on account platforms, and region-appropriate access to US services. The July 2026 review of the residential security series specifically reports Gemini, Claude and Steam currency working, along with AS9929 routing to all three Chinese carriers.

None of that is a purity certificate. Run the checks yourself on day one: look up the IP on ipinfo.io, run it through Scamalytics and IPQS, then log into the one platform you actually care about. Vendor screenshots are marketing material, and self-reported fraud scores across the industry aren't measured the same way.

## What it does not fix

**Platform enforcement above the IP level.** TikTok and similar platforms fingerprint at the ASN level. If enough accounts run on one residential ASN, the ASN itself starts collecting flags and every IP inside it degrades. A residential address buys you a better starting position, not immunity, and behaviour still gets weighed.

**Hardware value.** $25/month here buys 2 cores and 2 GB. SixTnet's own LAX-STARTER gives the same 2 cores, 2 GB, 40 GB and 5 TB for $200/year with DDoS protection, which is **$60 less per year** than the residential equivalent at $260. You are paying the premium for the IP, and the premium is roughly 30% on this tier. If the IP isn't the point, don't pay it.

**Unlimited traffic.** Residential plans are metered, 5 TB at entry. That covers account management, browsing and normal streaming. It does not cover 4K video running all day.

**Guaranteed unlocks.** SixTnet's published test results cover AI services and Steam currency. Netflix and Disney+ don't appear in them. Any provider claiming permanent Netflix access is overpromising, since the platforms change detection continuously.

## Picking by use case

**One TikTok or short-video account.** Residential-STARTER. 5 TB and a 2 Gbps port are more than one account generates; you're buying the IP and nothing else needs to be bigger.

**An account matrix.** This is where the single IPv4 per VPS becomes the whole decision. Five accounts means five VPS instances, or $125/month at the entry tier, because upgrading to MEDIUM buys cores and traffic rather than extra addresses. Budget for the IP count first and the specs second.

**AI tools and API exits.** STARTER again. ChatGPT, Claude and Gemini care about the region and reputation of the exit IP, not how many cores sit behind it.

**Mainland China latency.** IRVINE-PRO-STARTER at $350/year. The AS9929 route to all three carriers is the reason to pick it over the cheaper residential tier, and the whitelist-only access model suits a machine that only you connect to. Accept the balance-only refund policy going in.

**Streaming.** STARTER, then verify inside whatever refund terms you can get in writing. Start with the services SixTnet actually tested and work outward.

**Websites, bots, dev boxes, anything public.** Skip residential entirely. LAX-STARTER at $200/year has open ports, DDoS protection and 5 TB for less money.

## The yearly math

| Plan | Monthly | 12 × monthly | Annual price | Saving |
| --- | --- | --- | --- | --- |
| Residential-STARTER | $25 | $300 | $260 | $40 (13%) |
| Residential-MICRO | $45 | $540 | $460 | $80 (15%) |
| Residential-MEDIUM | $85 | $1,020 | $860 | $160 (16%) |
| Residential-LARGE | $165 | $1,980 | $1,660 | $320 (16%) |

The entry-tier annual discount is $40, about two months of service. That is not enough to justify committing a year before the IP has proven itself on your target platform, so start monthly and switch to annual once the checks come back clean. The pricing page presents the yearly figure as a reduction on twelve monthly payments rather than a first-term teaser, but it doesn't state renewal rates anywhere. Confirm that in the cart or a ticket rather than assuming the discount repeats.

👉 See the current monthly and annual rates on SixTnet's residential plans

## How SixTnet compares on price

| Provider | Entry price | What the entry tier includes |
| --- | --- | --- |
| IPRaft | $2.25/month | 1 core, 1 GB, 10 GB SSD, 1 TB, dual ISP native, Salt Lake City. Japan from $3/month plus $0.003/GB |
| SurferCloud | $16 per 30 days | 1 core, 2 GB, 40 GB SSD, 500 GB at 5 Mbps, dual ISP plus residential IP, Singapore (figures from a November 2024 post) |
| LisaHost | ¥68/month | 1 core, 1 GB, 10 GB NVMe, 1 TB, US 9929 dual ISP. Hong Kong line from ¥88/month |
| SixTnet | $25/month | 2 cores, 2 GB, 40 GB NVMe, 5 TB, residential IP, US |

SixTnet costs more at the door, and the extra buys 2 cores instead of 1 and 5 TB instead of 1 TB. Per terabyte of included traffic it lands well below the cheaper entries. If your only goal is one login test on one account, IPRaft's $2.25 tier is the cheaper way to find out whether a residential IP solves your problem at all. Once you're pushing more than a terabyte or two, the bundled traffic flips the comparison.

## Before you pay

1. Check stock on the tier you want; the four residential plans showed 0 available when this was written, and residential IPs are allocated in batches across the industry.
2. Open a ticket asking about refund terms and whether the IP gets replaced if it's already flagged on your target platform.
3. Ask which port SSH runs on, given that 80 and 443 are closed and port forwarding is configured through the client area.
4. Confirm IPv6 availability if you need it; the reviews say none.
5. Run ipinfo, Scamalytics and your platform login test within the first hours of delivery.
6. Count your accounts before choosing a plan, since each VPS carries one IPv4.

Only one US residential exit for an account or an AI subscription: Residential-STARTER at $25/month, billed monthly first. China-facing traffic with a locked-down machine: IRVINE-PRO-STARTER at $350/year. A website, a bot or a development box: LAX-STARTER at $200/year and no residential premium at all.

👉 Open SixTnet's VPS catalogue to check residential availability before the tier you want sells out again
