## DNS Log Analysis using Splunk

This project simulates analyzing a sample DNS log to identify anomalies, find top DNS sources, investigate suspicious domains, and extract fields using regex.

## Tools Used

- Splunk

## Steps Performed

- Uploaded the sample DNS log to Splunk.
- Searched for DNS events

```bash
source="dns.log.gz" host="kali" sourcetype="dns_log"

```

- Extracted relevant fields

```bash
source="dns.log.gz" host="kali" sourcetype="dns_log" | regex _raw="(?i)\\b(dns|domain|query|response|port 53)\\b"

```

- Identified anomalies such as spikes in DNS traffic

```bash
source="dns.log.gz" host="kali" sourcetype="dns_log" | stats count by fqdn

```

- Listed top DNS sources

```bash
source="dns.log.gz" host="kali" sourcetype="dns_log" | top fqdn, src_ip

```

- Investigated suspicious domains

```bash
source="dns.log.gz" host="kali" sourcetype="dns_log" fqdn="maliciousdomain.com"

```

## Outcome

Successfully analyzed the DNS log to find anomalies and spikes in DNS traffic.

Identified high-frequency queries and potential suspicious activity.

Investigated suspicious domains effectively.

## Key Learnings

Gain hands-on experience using Splunk for DNS log analysis.

Learned to extract and filter lof fields using regex.

Developed skills in detecting anomalies and investigating potential threats.
