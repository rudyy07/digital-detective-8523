# Mission 7 — How computers communicate

## 1. Task / objective

The objective of Mission 7 was to explain core networking terms (LAN, MAN, WAN, DNS, router, protocol, packet switching, and client-server), run macOS connectivity and DNS lookup tests on a public example domain (`example.com`) without publishing personal network details, and explain in 5–7 steps how a browser loads a website.

## 2. Work completed

- Completed the network-concepts table with explanations in my own words and simple examples.
- Ran `ping -c 3 example.com` to test network reachability and latency to a public domain.
- Ran `nslookup example.com` and `dig +noall +answer example.com A example.com AAAA` to inspect DNS records for `example.com`.
- Documented what connectivity tests and DNS lookups show (and their limits) without including any local IP address or Wi-Fi network details.
- Wrote a 6-step numbered walkthrough of what happens when a browser opens a website.

### Task 7.1 — Explain network concepts

| Concept | Explain it in your own words | Example |
|---|---|---|
| LAN | A network connecting devices in a small area such as a home, classroom, or computer lab. | Laptops and a printer connected to the same home Wi-Fi or lab switch. |
| MAN | A network that connects buildings across a city or a large university campus. | Campus-wide network linking engineering blocks and the library. |
| WAN | A network spanning long geographical distances across cities, countries, or continents. | The public internet connecting networks around the world. |
| DNS | The directory system that translates human-readable domain names into IP addresses. | Turning `example.com` into `104.20.23.154` so computers know where to send packets. |
| Router | A networking device that connects separate networks and forwards data packets toward their destination. | A home Wi-Fi router forwarding web requests between your laptop and your ISP. |
| Protocol | An agreed set of rules and formats that devices follow to communicate reliably. | HTTPS for encrypted web pages, or ICMP used by `ping`. |
| Packet switching | Splitting data into small numbered packets that travel across network paths and are reassembled at the destination. | Downloading a web page as small chunks rather than one continuous stream. |
| Client-server | A communication model where a client requests data or a service and a server responds with it. | Your web browser (client) requesting a page from GitHub's web server. |

### Task 7.2 — Observe network information

- **Connectivity test (`ping -c 3 example.com`):**
  - Observed `3 packets transmitted, 3 packets received, 0.0% packet loss`, with round-trip times between `5.635 ms` and `14.065 ms` (average `9.183 ms`) to `example.com` (`104.20.23.154`).
  - **What a connectivity test helps check:** It checks whether the host name resolves, whether packets can travel from my computer to the target server and back, whether any packets are dropped, and how fast the round-trip time is.
  - **What it cannot establish:** It cannot prove that the website or web server application (HTTP/HTTPS on port 80/443) is running or returning valid web pages, because `ping` only tests ICMP echo replies—and some live websites block ICMP `ping` packets even while working normally in a browser.
- **DNS lookup (`nslookup example.com` and `dig +noall +answer example.com A example.com AAAA`):**
  - Observed IPv4 (`A`) records `104.20.23.154` and `172.66.147.243` (TTL `300`), and IPv6 (`AAAA`) records `2606:4700:10::6814:179a` and `2606:4700:10::ac42:93f3`.
  - **What information a DNS lookup displays:** It displays the DNS server queried and the resolved IPv4 (`A`) and/or IPv6 (`AAAA`) addresses linked to that domain name (plus record caching time/TTL in `dig`).
  - **Role of DNS when entering a website name:** When you type a domain name like `example.com` into a browser, DNS translates that readable name into the numerical IP address your computer needs in order to route network packets to the right server.

### Task 7.3 — What happens when you open a website?

1. You type a website address (such as `https://example.com`) into your web browser, which acts as the **client**.
2. The browser checks its cache and asks **DNS** to translate the domain name into the website's IP address.
3. Once the **client** has the IP address, it prepares a web request following the HTTP/HTTPS **protocol** and splits the data into small packets.
4. Your local **router** forwards those packets out of your local network and across intermediate network routers on the internet toward the destination IP address.
5. The destination **server** receives the request packets, reassembles them, and processes what page or resource the **client** asked for.
6. The **server** sends back an HTTP/HTTPS **response** (HTML, CSS, images, and status code) across the network through routers back to your computer, and the browser renders the page on your screen.

## 3. Commands / tools used

- `ping -c 3 example.com` — Sent 3 ICMP echo packets to `example.com` to test reachability, packet loss, and round-trip time.
- `nslookup example.com` — Queried DNS to see the IPv4 addresses associated with `example.com`.
- `dig +noall +answer example.com A example.com AAAA` — Displayed both IPv4 (`A`) and IPv6 (`AAAA`) DNS records for `example.com`.

## 4. My understanding

Opening a website looks instant, but behind the scenes multiple layers work together: DNS turns a domain name into an IP address, routers forward packets across networks, and protocols like HTTPS define how the client and server talk. Testing with `ping`, `nslookup`, and `dig` shows how each layer can be checked separately when troubleshooting a connection.

## 5. Difficulties faced

No major difficulties.

## 6. How I resolved them

Not applicable.

## 7. Evidence / files

- `mission-07-networking/README.md` (network concepts table, privacy-safe `ping`/`nslookup`/`dig` observations, and 6-step website loading explanation)

## 8. Commit details

- **Commit message:** `Explain networking concepts and website communication`
- **Branch:** `main`
- **Push status:** Pushed to `origin/main` on GitHub (`rudyy07/digital-detective-8523`)
