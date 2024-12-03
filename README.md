
## Asnip

[![MIT License](https://img.shields.io/github/license/harleo/asnip?label=License&style=flat-square)](https://opensource.org/licenses/MIT)
[![Follow on Twitter](https://img.shields.io/twitter/follow/_harleo?color=00acee&label=Follow%20%40_harleo&style=flat-square)](https://twitter.com/_harleo)

Asnip retrieves all IPs of a target organization&mdash;used for attack surface mapping in reconnaissance phases.

It uses the IP or domain name and looks up the Autonomous System Number (ASN), retrieves the Classless Inter-Domain Routing (CIDR) subnet masks and converts them to IPs.

>IP / Domain &rarr; ASN &rarr; CIDRs &rarr; IPs

Please note that this technique only makes sense if the target has its own ASN. It is also advised to not perform tests on IP ranges that you do not have permission to.

### Installation
`go install github.com/cissusnar/asnip@latest`

_This tool requires [golang](https://golang.org/)_

### Options

```console
Usage:
  -t string
        Domain or IP address (Required)
  -p string
        Print results to console
```

### Example

```console
$ asnip -t google.com -p

[?] ASN: "15169" ORG: "GOOGLE, US"
8.8.4.0/24
--- snip ---
[:] Writing 616 CIDRs to file...
[:] Converting to IPs...
8.8.8.1
--- snip ---
[:] Writing 14725936 IPs to file...
[!] Done.
```

### Disclaimer
This tool must use an external API (which is subject to rate limiting) courtesy of HackerTarget to retrieve relevant data. The conversion of CIDRs to IPs will be done locally.

_Asnip is work in progress, if you make optimization changes yourself, you are invited to create a pull request or check the GitHub issues page&mdash;help is always appreciated._

---

&copy; github.com/harleo
