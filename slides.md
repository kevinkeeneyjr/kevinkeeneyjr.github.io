# ROCK
## Response Operations Collection Kit
### rocknsm.io
Kevin Keeney

***

### About Me
```notes
    - Entrepreneur
    - Leader
    - Idea Man
    - SysAdmin
    - Incident Response
    - Sales Engineer

```
---

#### I want to save the world!

***

***

## MOCYBER
### (Missouri National Guard Cyber Team)
![MOCYBER](images/cyber2.png)

```notes
    - National exercises /AND/ missions
    - Project C, Hawaii,Gordon, MD
    - CONOPS ("Drone Feed") & SOF Model
Humans are more important than Hardware.
Quality is better than Quantity.
Special Operations Forces cannot be mass produced.
Competent Special Operations Forces cannot be created after emergencies occur.
Most Special Operations require non-SOF assistance

```

---
### CAPES

*  Cyber Analytic Platform and Extraction Sensor

```notes
Overarching flyaway capability - malware analysis, chat, incident tracking, intel, workflow, etc

Docker, VM, standalone
```

---

### Predator Drone Feed

```notes
    - DBIR - 207 days "Flash to Bang" (MTTD)
    - Nationally losing our butts (Titan Rain, APT1, Enrgetic Bear, etc.)
    - Shortcomings of signatures (Purple Shirt)
    - TiVo for your network
    - "The Good Book"    
```

***

### ROCK

![ROCK Architecture](images/single_architecture.png)

```notes
    - Architecture Diagram
    - Data flow, component choice, years of changes
    - Scalability
    - Security - SELinux and STIG
    - Open source is free if your time is worthless
    - Build concept - Chef recipe - Reference architecture, not necessrily "go to war" ready
```

***

#### Architecture
*  PF_RING
*  Bro
*  Snort
*  Stenographer
*  Kafka
*  Logstash
*  Elasticsearch
*  Kibana

```notes
Pieces listed by name, I'll speak to each of these individually

```

---

### PF_RING

```notes
    - Provides load balancing capabilities for bro and via patched libpcap
    - Replaced in the near future with AF_PACKET
```

---

### Bro
#### Just a broverview

```notes
    - 20+ years old
    - Turing Complete programing language
    - Protocol Analyzers
    - Intel Framework (Actionable, reliable, and the risk of data librarians) Critical Stack
    - File Extraction (teksystems automator) (https://github.com/hosom/bro-file-extraction)
```

---

### Snort

```notes
    - The "grand dame" of IDS - most sec products on the market
    - Signature based detection
    - Preconfigured pulledpork (needs your OinkCode)
```

---

### Stenographer

```notes
    - PCAP capture
    - Presents a local API and stenoread tool
    - BPF syntax to extract just what you want
```

---

### Kafka

```notes
    - Provides elasticity (queueing) and fault tolerance to the stack
    - Big data pipeline tool
```

---

### Logstash

```notes
    - Data pipeline swiss army knife, many things, none well
    - Moves from kafka to ES with minor modifications (caveat emptor)
```

---

### Elasticsearch

```notes
    - Full text index of bro/snort data
    - Scales really well-ish
```

---

### Kibana

```notes
    - If the "interface is the product", this is it.
    - Search, share searches, visualizations, dashboards
```

***

### (Bare) Minimum Hardware
*  8GB of RAM
*  2 CPU Cores
*  Disk (Space and IOPS)

```notes
    - ES/Kafka/LS all java.  Hungry hippos of ram.
    - Kafka and ES can batter disk
```

***

### But does it scale?

```notes
    - Tiny example 16GB, decent IOPS (m.2 SSD), and dual core  i3.  1Gbps
    - Regularly test SimpleRock stack with 3-4 Gbps traffic, though storage wouldn't last long.
    - Several places to break it apart...
```

---

### Scale out Elasticsearch

```notes
    - 64-96GB of RAM, 32 for ES, 32 for Lucene, remainder for other services
    - Add them in twos
    - Three factors to consider - ingest rate, search volume, and retention time
```

---

### Partition Kafka topic & increase logstash workers

```notes
    - Once ES is ready to receive it, this increases throughput capability
```

***

### Roadmap

```notes
    - Emerson FSF (Lockheed's LaikaBoss)
    - Fix Snort or add Snorby
    - Built-in Dashboards and analytics
    - Better segmentation and ISO
```

---

### How do I get started?

```notes
    - git clone/vagrant up
    - minimal/update/etc
    - Plan a big deployment
    - File issues and PR's
```

---

## Questions?

---

### Thank you
#### rocknsm.io
#### @rocknsm
