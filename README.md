<div align="center">

# ⚡ Aditya Dahale
### Systems & AI Software Engineer • Ultra-Low Latency Infrastructure • Open Source

[![Live Portfolio](https://img.shields.io/badge/🌐_Portfolio-Live_Site-10b981?style=for-the-badge)](https://aditya-9-6.github.io/Aditya_dahale-portfolio/)
[![Resume PDF](https://img.shields.io/badge/📄_Resume-Download_1--Page_PDF-blue?style=for-the-badge)](https://aditya-9-6.github.io/Aditya_dahale-portfolio/Aditya_Dahale_Resume.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/aditya-dahale-207208aditya)
[![GitHub Stars](https://img.shields.io/badge/Open_Source_Impact-180,000+_Stars-f59e0b?style=for-the-badge&logo=github)](https://github.com/aditya-9-6)

<br/>

> **Building hyper-performance edge security engines, sub-microsecond network inspection runtimes, and resilient systems software in Rust, C++, and Linux.**

</div>

---

### 🛡️ Featured Systems Project: [Spryzen+](https://github.com/Aditya-9-6/spryzen-test-1)
> **Hyper-Performance Network Security & Telemetry Engine** — Zero-Allocation Packet Processing at Line Rate.

- **4.83 Million RPS** packet ingestion throughput on single-node bare metal.
- **207 ns P99 latency** with zero dynamic heap allocations on the packet wire path (`Cow::Borrowed` stack slices).
- **27.99 ns Zero-Alloc Fast-Path Normalization**: Bypasses heavy regex and unicode normalization passes via a compile-time 256-byte lookup table (`NEEDS_DEEP_NORM_TABLE`).
- **0.00 ns $O(1)$ RISKY_CHAR_TABLE**: Replaced 24 chained character branches with single-instruction vectorized byte lookups.
- **Lock-Free Concurrency**: Ring buffers and atomic ring queue scheduling eliminating thread context-switching locks.
- **Adaptive Rayon Bulkhead**: Inline sub-microsecond processing for standard payloads ($\le 8\text{KB}$); bulkhead thread-pool isolation for jumbo payloads ($> 8\text{KB}$) protecting Tokio worker threads from ReDoS.

🔗 **Code Repository**: [`Aditya-9-6/spryzen-test-1`](https://github.com/Aditya-9-6/spryzen-test-1) &nbsp;|&nbsp; 📊 **Benchmarks**: [`Aditya-9-6/Spryzen-Benchmarks`](https://github.com/Aditya-9-6/Spryzen-Benchmarks)

---

### ⚡ Paradigm Core Ethereum Infrastructure Contributions (Reth • Alloy • Foundry)

Production pull requests fixing critical synchronization, edge-case network recovery, and path injection vulnerabilities across Paradigm's core Rust ecosystem:

| Project & Repo | Pull Request | Impact & Technical Achievement | Status |
| :--- | :--- | :--- | :---: |
| **Paradigm Reth**<br/>`paradigmxyz/reth`<br/>*(7,000+ ★)* | [**PR #27049**](https://github.com/paradigmxyz/reth/pull/27049) | **Snapshot manifest validation & zero-chunk division guard**: Enforced `SnapshotManifest::validate()` to reject malformed manifests with `blocks_per_file == 0` prior to expansion. Hardened `ChunkedArchive::num_chunks()` and `chunk_relative_path()` with saturating arithmetic to prevent zero-division panics during snapshot downloads. | ![PR Open](https://img.shields.io/badge/PR-Open_•_Review_Requested-blue?style=flat-square) |
| **Alloy Core SDK**<br/>`alloy-rs/alloy`<br/>*(1,400+ ★)* | [**PR #4191**](https://github.com/alloy-rs/alloy/pull/4191) | **Watch stream heartbeat recovery**: Fixed silent stream freeze in `PendingTransactionBuilder::watch` (#4181, #3881) when HTTP pollers skip the exact mined block due to network jitter. Automatically scans skipped block ranges across poll heartbeats to ensure pending transactions are never hung indefinitely. | ![PR Open](https://img.shields.io/badge/PR-Open_•_Review_Requested-blue?style=flat-square) |
| **Foundry**<br/>`foundry-rs/foundry`<br/>*(16,000+ ★)* | [**PR #16707**](https://github.com/foundry-rs/foundry/pull/16707) | **Chisel NTFS alternate data stream isolation**: Hardened `validate_session_id` in `crates/chisel` to reject `:` alongside directory traversal characters (`/`, `\`), preventing session writes from escaping cache enumeration into Windows NTFS Alternate Data Streams (`chisel-foo:bar.json`). | ![PR Open](https://img.shields.io/badge/PR-Open_•_Review_Requested-blue?style=flat-square) |

---

### 🌟 Tier-1 Systems Open-Source Contributions

Direct contributions to mission-critical infrastructure projects powering production services globally:

| Project & Repo | Pull Request | Impact & Technical Achievement | Status |
| :--- | :--- | :--- | :---: |
| **Cloudflare Pingora**<br/>`cloudflare/pingora`<br/>*(22,000+ ★)* | [**PR #996**](https://github.com/cloudflare/pingora/pull/996) | **RFC 9110 §15.6.6 upstream timeout mapping**: Resolved upstream timeout classification in Cloudflare's core reverse proxy. Mapped upstream connect, TLS handshake, and read/write timeouts to `504 Gateway Timeout` instead of generic `502 Bad Gateway`. | ![CI](https://img.shields.io/badge/CI-100%25_Green_(4/4)-brightgreen?style=flat-square) |
| **Tokio Async Runtime**<br/>`tokio-rs/tokio`<br/>*(27,000+ ★)* | [**PR #8405**](https://github.com/tokio-rs/tokio/pull/8405) | **Semaphore integer overflow fix**: Resolved critical permit-leak bug in `SemaphorePermit::merge` where permit counts exceeding `u32::MAX` wrapped and permanently leaked permits upon drop. Converted storage to `usize` with safe checked arithmetic. | ![Merged](https://img.shields.io/badge/Merged-by_Darksonn-8957e5?style=flat-square) |
| **Astral uv**<br/>`astral-sh/uv`<br/>*(45,000+ ★)* | [**PR #21457**](https://github.com/astral-sh/uv/pull/21457) | **Cross-process file lock timeout propagation**: Decoupled lock acquisition from static timeouts by threading configurable timeout options through `EnvironmentOptions` across Astral's entire workspace toolchain. Passed all 55 CI matrix suites across 11 OS/arch targets. | ![CI](https://img.shields.io/badge/CI-100%25_Green_(58/58)-brightgreen?style=flat-square) |
| **Google Comprehensive Rust**<br/>`google/comprehensive-rust`<br/>*(28,000+ ★)* | [**PR #3275**](https://github.com/google/comprehensive-rust/pull/3275) | **LLVM Undefined Behavior modeling**: Accurately modeled language-level UB using intrinsic `i32::unchecked_add` in unsafe courseware modules per Google Staff Engineer design review. | ![CI](https://img.shields.io/badge/CI-Green_•_CLA_Signed-brightgreen?style=flat-square) |
| **FoxIO JA4 Fingerprinting**<br/>`FoxIO-LLC/ja4`<br/>*(Official Standard)* | [**PR #312**](https://github.com/FoxIO-LLC/ja4/pull/312)<br/>[**PR #314**](https://github.com/FoxIO-LLC/ja4/pull/314) | **Zero-allocation HTTP/1 header filtering & hex-digest encoding**: Eliminated temporary `String` allocations during HTTP/1 header checks and optimized JA4/JA4X hash12 by directly hex-encoding 6-byte raw digest slices. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **smoltcp**<br/>`smoltcp-rs/smoltcp`<br/>*(Standalone TCP/IP stack)* | [**PR #1194**](https://github.com/smoltcp-rs/smoltcp/pull/1194) | **TCP stack socket management**: Fixed core edge cases in standalone packet reassembly and transmission queues for embedded systems. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **SmartCore**<br/>`smartcorelib/smartcore` | [**PR #386**](https://github.com/smartcorelib/smartcore/pull/386) | **SIMD-accelerated math operations**: Optimized linear algebra and matrix kernel calculations in pure Rust ML suite. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **MaxMindDB**<br/>`oschwald/maxminddb-rust` | [**PR #120**](https://github.com/oschwald/maxminddb-rust/pull/120) | **Zero-allocation IP metadata lookup**: Eliminated redundant heap buffer clones in high-throughput GeoIP lookup tables. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |

---

### 💻 Technical Toolbelt

```
Languages:        Rust (Advanced / Unsafe / Systems), C/C++, Python, Go, SQL, Bash
Systems & Perf:   Zero-Allocation Architecture, Lock-Free Ring Buffers, SIMD / LUTs, Rayon Bulkheads, eBPF
Networking:       TLS 1.3 / JA4 Fingerprinting, RFC 9110 HTTP/1 & HTTP/2, TCP/IP, Smoltcp, Pingora, Reverse Proxies
Concurrency:      Tokio Async Runtime, Epoll, Non-blocking I/O, Atomics, Mutex-Free Pipelines
Cloud & Infra:    Docker, Kubernetes, AWS, Linux Kernel Internals, GitHub Actions CI/CD
AI & Backend:     RAG Systems, Vector Databases, FastEmbed, LangChain, FastAPI, Local LLM Inference Engines
```

---

### 📬 Connect & Collaborate

- 🌐 **Personal Portfolio**: [aditya-9-6.github.io/Aditya_dahale-portfolio](https://aditya-9-6.github.io/Aditya_dahale-portfolio/)
- 📄 **1-Page Resume (PDF)**: [Download Resume](https://aditya-9-6.github.io/Aditya_dahale-portfolio/Aditya_Dahale_Resume.pdf)
- 💼 **LinkedIn**: [linkedin.com/in/aditya-dahale-207208aditya](https://www.linkedin.com/in/aditya-dahale-207208aditya/)
- ✉️ **Email**: [adityadahale96@gmail.com](mailto:adityadahale96@gmail.com)
