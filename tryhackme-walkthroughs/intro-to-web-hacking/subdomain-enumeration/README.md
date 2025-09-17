Subdomain Enumeration — TryHackMe

## Overview
Subdomain enumeration finds valid subdomains of a target to expand the attack surface (APIs, admin portals, staging sites). Use a mix of OSINT, brute force, and host-header (vhost) techniques for complete coverage.

## Key Techniques
- **Certificate Transparency (crt.sh):** search CT logs for certs issued to subdomains.
- **Search engines (Google dorking):** `site:*.domain.com -site:www.domain.com`.
- **Passive OSINT tools:** `subfinder`, `amass`, `sublist3r`.
- **Brute-force DNS:** wordlist-based DNS queries (e.g., `dnsrecon`, `massdns`).
- **Virtual host (Host header) fuzzing:** send Host header variations to an IP to discover vhosts (use `ffuf`).

## Useful commands
# crt.sh - use the web UI: https://crt.sh (filter by date, issuer)
# Google dork example:
# site:*.tryhackme.com -site:www.tryhackme.com

# Sublist3r (OSINT aggregation)
sublist3r -d domain.com -o sublist.txt

# ffuf host-header vhost fuzzing
ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt \
     -H "Host: FUZZ.acmeitsupport.thm" \
     -u http://10.201.9.186

# filtered ffuf (ignore common size)
ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt \
     -H "Host: FUZZ.acmeitsupport.thm" \
     -u http://10.201.9.186 -fs {size}
