<div align="center">

# ⚡ Aditya Dahale
### Systems & AI Software Engineer • Ultra-Low Latency Infrastructure • Open Source

[![Live Portfolio](https://img.shields.io/badge/🌐_Portfolio-Live_Site-10b981?style=for-the-badge)](https://aditya-9-6.github.io/Aditya_dahale-portfolio/)
[![Resume PDF](https://img.shields.io/badge/📄_Resume-Download_1--Page_PDF-blue?style=for-the-badge)](https://aditya-9-6.github.io/Aditya_dahale-portfolio/Aditya_Dahale_Resume.pdf)
[![Merged PRs](https://img.shields.io/badge/Open_Source-11+_Upstream_Contributions-8957e5?style=for-the-badge&logo=git-merge)](https://github.com/aditya-9-6)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/aditya-dahale-207208aditya)
[![GitHub Stars](https://img.shields.io/badge/Impact-200,000+_Stars-f59e0b?style=for-the-badge&logo=github)](https://github.com/aditya-9-6)

<br/>

> **Systems software engineer focused on Rust, Linux kernel networking, eBPF/XDP, and high-performance distributed systems. Founder of Spryzen, architecting low-latency packet-processing and security proxy infrastructure reaching 6.92M PPS and 4.83M sustained RPS. Author of 11+ upstream systems contributions merged and reviewed across Tokio, Wasmtime, smoltcp, Foundry, Cloudflare Pingora, and Hyper.**

</div>

---

### 🛡️ Featured Systems Project: [Spryzen](https://github.com/Aditya-9-6/spryzen)
> **Hyper-Performance Network Security & Telemetry Engine** — Zero-Allocation Packet Processing at Line Rate.

- ⚡ **6.92 Million PPS**: L3/L4 wire-speed packet filtering via eBPF/XDP kernel bypass (Aegis XDP), dropping volumetric DDoS flood frames directly in the NIC DMA ring (`XDP_DROP`).
- 🚀 **4.83 Million RPS**: Sustained horizontal line-rate throughput across multi-core bare-metal proxy cluster node deployment (~200k–240k RPS per dedicated vCPU).
- 🔬 **18.54 ns (0.0185 µs)**: Pure CPU zero-allocation inspection latency (**53.9M ops/sec** single-core capacity) verified across 1,000,000 requests.
- 🛡️ **100.00% OWASP CRS Mitigation Score**: 39/39 attack vectors blocked with **0.00% False Positive Rate** across clean traffic.
- 💉 **Automated Penetration & Fuzzing Verified**: Intercepts `sqlmap` & `nikto`, fingerprints via `wafw00f`, and survived 10,000 extreme packet mutations with 0 crashes.
- **Lock-Free Concurrency & Zero-Allocation**: Ring buffers, cache-pinned 256-byte branchless LUTs, and thread-local L1 hash caches with 0 bytes of heap allocation on the hot path.

🔗 **Code Repository**: [`Aditya-9-6/spryzen`](https://github.com/Aditya-9-6/spryzen) &nbsp;|&nbsp; 📊 **Live Benchmarks & CI Telemetry**: [`Aditya-9-6/Spryzen-Benchmarks`](https://github.com/Aditya-9-6/Spryzen-Benchmarks)

---

### ⚡ Paradigm Core Ethereum Infrastructure Contributions (Reth • Alloy • Foundry)

Production pull requests fixing critical synchronization, edge-case network recovery, and path injection vulnerabilities across Paradigm's core Rust ecosystem:

| Project & Repo | Pull Request | Impact & Technical Achievement | Status |
| :--- | :--- | :--- | :---: |
| **Foundry**<br/>`foundry-rs/foundry`<br/>*(16,000+ ★)* | [**PR #16707**](https://github.com/foundry-rs/foundry/pull/16707) | **Chisel NTFS alternate data stream isolation**: Hardened `validate_session_id` in `crates/chisel` to reject `:` alongside directory traversal characters (`/`, `\`), preventing session writes from escaping cache enumeration into Windows NTFS Alternate Data Streams (`chisel-foo:bar.json`). | ![Merged](https://img.shields.io/badge/Merged-by_foundry--rs-8957e5?style=flat-square) |
| **Paradigm Reth**<br/>`paradigmxyz/reth`<br/>*(7,000+ ★)* | [**PR #27049**](https://github.com/paradigmxyz/reth/pull/27049) | **Snapshot manifest validation & zero-chunk division guard**: Enforced `SnapshotManifest::validate()` to reject malformed manifests with `blocks_per_file == 0` prior to expansion. Hardened `ChunkedArchive::num_chunks()` and `chunk_relative_path()` with saturating arithmetic to prevent zero-division panics during snapshot downloads. | ![PR Open](https://img.shields.io/badge/PR-Open_•_Review_Requested-blue?style=flat-square) |
| **Alloy Core SDK**<br/>`alloy-rs/alloy`<br/>*(1,400+ ★)* | [**PR #4191**](https://github.com/alloy-rs/alloy/pull/4191) | **Watch stream heartbeat recovery**: Fixed silent stream freeze in `PendingTransactionBuilder::watch` (#4181, #3881) when HTTP pollers skip the exact mined block due to network jitter. Automatically scans skipped block ranges across poll heartbeats to ensure pending transactions are never hung indefinitely. | ![PR Open](https://img.shields.io/badge/PR-Open_•_Review_Requested-blue?style=flat-square) |

---

### 🌟 Tier-1 Systems Open-Source Contributions (Merged & Active)

Direct contributions to mission-critical infrastructure projects powering production services globally:

| Project & Repo | Pull Request | Impact & Technical Achievement | Status |
| :--- | :--- | :--- | :---: |
| **smoltcp**<br/>`smoltcp-rs/smoltcp`<br/>*(Standalone TCP/IP stack)* | [**PR #1194**](https://github.com/smoltcp-rs/smoltcp/pull/1194)<br/>[**PR #1204**](https://github.com/smoltcp-rs/smoltcp/pull/1204)<br/>[**PR #1208**](https://github.com/smoltcp-rs/smoltcp/pull/1208) | **Zero-allocation wire parser & connection state resilience**: Engineered single-pass zero-alloc `TcpOptionSummary` parser (#1194, Merged); prevented idle connection abort on user timeout (#1204, Open); resolved buffer padding in `PacketBuffer::is_empty` eliminating busy loops (#1208, Open). | ![Merged](https://img.shields.io/badge/PR_#1194-Merged-8957e5?style=flat-square)&nbsp;![Open](https://img.shields.io/badge/PRs-Active_Review-blue?style=flat-square) |
| **Bytecode Alliance Wasmtime**<br/>`bytecodealliance/wasmtime`<br/>*(16,000+ ★)* | [**PR #14387**](https://github.com/bytecodealliance/wasmtime/pull/14387)<br/>[**PR #14515**](https://github.com/bytecodealliance/wasmtime/pull/14515) | **WASI POSIX symlink resolution & CLI export validation**: Fixed directory resolution in manual resolver when `FollowSymlinks::No` is set with trailing slashes preventing erroneous `ENOTDIR` failures (#14387, Merged by Alex Crichton); listed supported exports in error message when failing to run/serve component (#14515, Open). | ![Merged](https://img.shields.io/badge/PR_#14387-Merged-8957e5?style=flat-square)&nbsp;![Open](https://img.shields.io/badge/PR_#14515-Open-blue?style=flat-square) |
| **Tokio Async Runtime**<br/>`tokio-rs/tokio`<br/>*(27,000+ ★)* | [**PR #8405**](https://github.com/tokio-rs/tokio/pull/8405)<br/>[**PR #8575**](https://github.com/tokio-rs/tokio/pull/8575) | **Semaphore overflow fix & buffered relative seek bounds**: Resolved critical permit-leak bug in `SemaphorePermit::merge` exceeding `u32::MAX` with checked `usize` arithmetic (#8405, Merged by Darksonn); prevented integer overflow on buffered relative seek (#8575, Reviewed). | ![Merged](https://img.shields.io/badge/PR_#8405-Merged-8957e5?style=flat-square)&nbsp;![Reviewed](https://img.shields.io/badge/PR_#8575-Reviewed-8957e5?style=flat-square) |
| **Cloudflare Pingora**<br/>`cloudflare/pingora`<br/>*(22,000+ ★)* | [**PR #1039**](https://github.com/cloudflare/pingora/pull/1039)<br/>[**PR #1000**](https://github.com/cloudflare/pingora/pull/1000)<br/>[**PR #996**](https://github.com/cloudflare/pingora/pull/996) | **Header trace panic guard & configurable parser bounds**: Prevented panic on non-UTF-8 response headers in HTTP/1 trace logging (#1039, Open); engineered configurable HTTP/1 parser limits (#1000); mapped upstream connect, TLS handshake, and read/write timeouts to `504 Gateway Timeout` (#996). | ![CI](https://img.shields.io/badge/CI-100%25_Green-brightgreen?style=flat-square)&nbsp;![Open](https://img.shields.io/badge/PR_#1039-Open-blue?style=flat-square) |
| **Hyper HTTP Engine**<br/>`hyperium/hyper`<br/>*(15,000+ ★ • 100M+ DL)* | [**PR #337**](https://github.com/hyperium/hyper-util/pull/337)<br/>[**PR #4183**](https://github.com/hyperium/hyper/pull/4183) | **Protocol detection timeout bounds & header size enforcement**: Bounded automatic server protocol detection with `read_version_timeout` in hyper-util (#337, Open); added server & client builder APIs for strict RFC 6585 §5 (431 Too Large) rejection in core hyper (#4183, In Review). | ![PR Open](https://img.shields.io/badge/PRs-In_Review-blue?style=flat-square) |
| **Fly.io Corrosion**<br/>`superfly/corrosion`<br/>*(Distributed SQLite cluster)* | [**PR #559**](https://github.com/superfly/corrosion/pull/559)<br/>[**PR #578**](https://github.com/superfly/corrosion/pull/578) | **PostgreSQL wire protocol rollback handling & crash resilience**: Handled PostgreSQL wire AST rollback recovery in corro-pg (#559, Merged); eliminated schema migration panics with graceful error propagation across agent nodes (#578). | ![Merged](https://img.shields.io/badge/PR_#559-Merged-8957e5?style=flat-square) |
| **FoxIO JA4 Fingerprinting**<br/>`FoxIO-LLC/ja4`<br/>*(Official Standard)* | [**PR #312**](https://github.com/FoxIO-LLC/ja4/pull/312)<br/>[**PR #314**](https://github.com/FoxIO-LLC/ja4/pull/314)<br/>[**PR #327**](https://github.com/FoxIO-LLC/ja4/pull/327) | **Zero-allocation HTTP/1 header filtering & ALPN spec compliance**: Eliminated temporary `String` allocations (#312, Merged); hex-encoded raw digest slices (#314, Merged); handled single-character ALPN according to spec (#327, Open). | ![Merged](https://img.shields.io/badge/Merged-2x-8957e5?style=flat-square)&nbsp;![Open](https://img.shields.io/badge/PR_#327-Open-blue?style=flat-square) |
| **Google Comprehensive Rust**<br/>`google/comprehensive-rust`<br/>*(28,000+ ★)* | [**PR #3275**](https://github.com/google/comprehensive-rust/pull/3275) | **LLVM Undefined Behavior modeling**: Accurately modeled language-level UB using intrinsic `i32::unchecked_add` in unsafe courseware modules per Google Staff Engineer design review. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **Fly.io LTX**<br/>`superfly/ltx`<br/>*(SQLite transaction file format)* | [**PR #102**](https://github.com/superfly/ltx/pull/102)<br/>[**PR #104**](https://github.com/superfly/ltx/pull/104) | **Stream decoder integrity & zero-page checksum fix**: Enforced strict payload validation for empty block headers preventing stream corruptions (#102); resolved edge-case panic and trailer generation on zero-page files with `NoChecksum: true` (#104). | ![CI](https://img.shields.io/badge/CI-100%25_Green-brightgreen?style=flat-square) |
| **BranchBase**<br/>`oscarbol09/branchbase` | [**PR #126**](https://github.com/oscarbol09/branchbase/pull/126) | **Custom configuration file path CLI flag**: Added `--config / -c` flag to allow custom configuration file paths in BranchBase CLI (#114). | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **Astral uv**<br/>`astral-sh/uv`<br/>*(45,000+ ★)* | [**PR #21457**](https://github.com/astral-sh/uv/pull/21457) | **Cross-process file lock timeout propagation**: Decoupled lock acquisition from static timeouts by threading configurable timeout options through `EnvironmentOptions` across Astral's entire workspace toolchain. Passed all 55 CI matrix suites. | ![CI](https://img.shields.io/badge/CI-100%25_Green_(58/58)-brightgreen?style=flat-square) |
| **Turso libSQL**<br/>`tursodatabase/libsql`<br/>*(14,000+ ★)* | [**PR #2280**](https://github.com/tursodatabase/libsql/pull/2280) | **Default WAL journal mode for local databases**: Enforced Write-Ahead Logging (WAL) concurrency as default for local SQLite instances, preventing database locks under concurrent access. All 12 CI suites passed. | ![CI](https://img.shields.io/badge/CI-100%25_Green-brightgreen?style=flat-square) |
| **RuView Firmware**<br/>`RuView`<br/>*(Embedded Systems)* | [**PR #1**](https://github.com/Aditya-9-6/RuView/pull/1) | **Hardware base MAC entropy for device fingerprints & host C unit tests**: Used ESP32 hardware base MAC as entropy for PSA SHA-256 device onboarding fingerprints (`serial_onboarding.c`), with zero-dependency host C unit testing harness. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **SmartCore**<br/>`smartcorelib/smartcore` | [**PR #386**](https://github.com/smartcorelib/smartcore/pull/386) | **Capacity pre-allocation in ensemble trees**: Optimized ensemble tree training cycles by pre-allocating exact vector capacities in Random Forest models, eliminating repeated heap memory reallocations. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **MaxMindDB**<br/>`oschwald/maxminddb-rust` | [**PR #120**](https://github.com/oschwald/maxminddb-rust/pull/120) | **Zero-allocation IP metadata lookup**: Accelerated GeoIP binary lookups using native big-endian byte decoding (`u32::from_be_bytes`), enabling single-CPU-instruction decoding of 32-bit database nodes. | ![Merged](https://img.shields.io/badge/Status-Merged-8957e5?style=flat-square) |
| **Juspay Hyperswitch**<br/>`juspay/hyperswitch`<br/>*(14,000+ ★)* | [**PR #14551**](https://github.com/juspay/hyperswitch/pull/14551) | **Connector capture synchronization**: Stopped declaring sequential automatic capture for CoinGate connector to align with asynchronous webhook lifecycles. | ![Open](https://img.shields.io/badge/PR_#14551-Open-blue?style=flat-square) |
| **Kestra**<br/>`kestra-io/kestra`<br/>*(20,000+ ★)* | [**PR #20051**](https://github.com/kestra-io/kestra/pull/20051) | **UI layout stability**: Prevented layout shift on log body line clamp toggle across log viewer components. | ![Open](https://img.shields.io/badge/PR_#20051-Open-blue?style=flat-square) |

---

### 💻 Technical Toolbelt

```
Languages:        Rust (Advanced / Unsafe / Systems), C/C++, Python, Go, SQL, Bash
Systems & Perf:   Zero-Allocation Architecture, Lock-Free Ring Buffers, SIMD / LUTs, Rayon Bulkheads, eBPF/XDP
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
