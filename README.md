<div align="center">

# ⚡ Aditya Dahale
### Systems & Infrastructure Software Engineer • Rust • Linux Kernel Networking • Distributed Systems

[![Live Portfolio](https://img.shields.io/badge/🌐_Portfolio-Live_Site-10b981?style=for-the-badge)](https://aditya-9-6.github.io/Aditya_dahale-portfolio/)
[![Resume PDF](https://img.shields.io/badge/📄_Resume-Download_1--Page_PDF-0284c7?style=for-the-badge)](https://aditya-9-6.github.io/Aditya_dahale-portfolio/Aditya_Dahale_Resume.pdf)
[![Merged PRs](https://img.shields.io/badge/Open_Source-15+_Merged_Upstream_PRs-8957e5?style=for-the-badge&logo=git-merge)](https://github.com/Aditya-9-6)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/aditya-dahale-207208aditya)
[![GitHub Stars](https://img.shields.io/badge/Impact-250,000+_Stars-f59e0b?style=for-the-badge&logo=github)](https://github.com/Aditya-9-6)

<br/>

> **Systems software engineer specializing in Rust, Linux kernel networking (eBPF/XDP), zero-copy protocols, and high-throughput distributed infrastructure. Contributor to Tier-1 systems runtimes powering global infrastructure—including Tokio, Hyper, Wasmtime, smoltcp, Cloudflare Pingora, and Foundry. Founder of Spryzen, DevProxy, and GossipMesh.**

</div>

---

## 🚀 Flagship Systems & Infrastructure Projects

### 🛡️ 1. [Spryzen](https://github.com/Aditya-9-6/spryzen) — Hyper-Performance Network Security & Telemetry Engine
> **Zero-Allocation Packet Processing & Line-Rate Reverse Proxy at Bare-Metal Scale.**

- ⚡ **6.92 Million PPS**: L3/L4 wire-speed packet filtering via eBPF/XDP kernel bypass (`Aegis XDP`), dropping volumetric DDoS flood frames directly in the NIC DMA ring (`XDP_DROP`).
- 🚀 **4.83 Million RPS**: Sustained horizontal line-rate throughput across multi-core proxy cluster deployments (~200k–240k RPS per dedicated vCPU).
- 🔬 **18.54 ns (0.0185 µs)**: Pure CPU zero-allocation inspection latency (**53.9M ops/sec** single-core capacity) verified across 1,000,000 requests.
- 🛡️ **100.00% OWASP CRS Mitigation**: 39/39 attack vectors blocked with **0.00% False Positive Rate** across clean traffic.
- 🔒 **Zero-Allocation Memory Safety**: Cache-pinned 256-byte branchless LUTs, lock-free ring buffers, and SIMD fast-path normalization without dynamic heap allocation on the hot path.
- 🔗 **Repo**: [`Aditya-9-6/spryzen`](https://github.com/Aditya-9-6/spryzen) &nbsp;|&nbsp; 📊 **Benchmarks**: [`Aditya-9-6/Spryzen-Benchmarks`](https://github.com/Aditya-9-6/Spryzen-Benchmarks)

---

### 🌐 2. [DevProxy](https://github.com/Aditya-9-6/DevProxy) — Next-Gen High-Throughput Developer Reverse Proxy
> **Zero-Allocation Streaming, Deterministic HAR Playback & Enterprise Observability.**

- 📼 **Deterministic HAR Recording & Playback**: Lossless HTTP/1.1–HTTP/2 session capture and byte-for-byte deterministic replaying with millisecond timing fidelity.
- 🔍 **Next-Gen TLS Telemetry**: Real-time **JA3 / JA4** TLS client hello fingerprinting and OpenTelemetry distributed tracing across all proxy hops.
- 🛡️ **Inline Defense & Data Leak Guard**: Real-time PII redaction, LLM token tracking, and GraphQL attack prevention built with streaming zero-allocation decoders.
- ⚡ **Chaos & Mock Simulation**: Low-overhead network throttling, latency injection, and Aho-Corasick pattern matchers for resilience engineering under load.
- 🔗 **Repo**: [`Aditya-9-6/DevProxy`](https://github.com/Aditya-9-6/DevProxy)

---

### 🧠 3. [GossipMesh](https://github.com/Aditya-9-6/GossipMesh) — Decentralized AST-Aware Autonomous Multi-Agent Mesh
> **Symbol-Aware Context Engine, Memetic Knowledge Base & Two-Tier Model Routing.**

- 🧬 **True Memetic Memory**: Epistemic peer digest gossip protocol synchronizing architectural invariants and operational learnings across distributed agent nodes.
- 🎯 **AST & Symbol-Aware Context Extraction**: Replaces brute-force file dumps with precise abstract syntax tree context pruning, reducing token overhead by 60%.
- ⚡ **Two-Tier Model Routing (Brains vs. Muscle)**: Dynamically routes heavy architectural reasoning vs. fast syntax fixing across cost/latency optimal LLM endpoints.
- 🛡️ **Autonomous PR Quality Gate**: Automated continuous evaluation, semantic caching, human-in-the-loop guardrails, and self-healing CI loops.
- 🔗 **Repo**: [`Aditya-9-6/GossipMesh`](https://github.com/Aditya-9-6/GossipMesh)

---

## 🌟 Tier-1 Open-Source Systems Contributions (Merged & Active)

Production contributions merged and reviewed across core runtimes and protocols powering millions of servers:

| Repository & Ecosystem | Pull Request | Impact & Technical Achievement | Status |
| :--- | :--- | :--- | :---: |
| **Tokio Async Runtime**<br/>`tokio-rs/tokio`<br/>*(27,000+ ★)* | [**PR #8405**](https://github.com/tokio-rs/tokio/pull/8405) | **Semaphore integer overflow & permit leak**: Resolved critical permit-leak bug in `SemaphorePermit::merge` exceeding `u32::MAX` by transitioning to checked `usize` arithmetic; verified under Tokio's Loom concurrency CI. Merged by maintainer Alice Ryhl. | ![Merged](https://img.shields.io/badge/PR_#8405-Merged-8957e5?style=flat-square&logo=git-merge) |
| **Hyper HTTP Engine**<br/>`hyperium/hyper`<br/>*(15,000+ ★ • 100M+ DL)* | [**PR #4183**](https://github.com/hyperium/hyper/pull/4183)<br/>[**PR #337**](https://github.com/hyperium/hyper-util/pull/337) | **RFC 6585 max_header_size protocol enforcement**: Added server & client builder APIs for strict RFC 6585 §5 (`431 Request Header Fields Too Large`) rejection, zero-copy stream guards, and chunked trailer decoder limits across 180+ tests. | ![Merged](https://img.shields.io/badge/PR_#4183-Merged-8957e5?style=flat-square&logo=git-merge) |
| **Bytecode Alliance Wasmtime**<br/>`bytecodealliance/wasmtime`<br/>*(17,000+ ★)* | [**PR #14387**](https://github.com/bytecodealliance/wasmtime/pull/14387) | **POSIX trailing slash symlink resolution in WASI**: Fixed directory resolution in manual filesystem resolver when `FollowSymlinks::No` is set with trailing slashes, preventing erroneous `ENOTDIR` failures in WASI runtimes. Merged by Alex Crichton. | ![Merged](https://img.shields.io/badge/PR_#14387-Merged-8957e5?style=flat-square&logo=git-merge) |
| **smoltcp Network Stack**<br/>`smoltcp-rs/smoltcp`<br/>*(Zero-copy embedded TCP/IP)* | [**PR #1194**](https://github.com/smoltcp-rs/smoltcp/pull/1194)<br/>[**PR #1208**](https://github.com/smoltcp-rs/smoltcp/pull/1208) | **Zero-allocation wire parser & 100% CPU busy-loop fix**: Engineered single-pass zero-allocation `TcpOptionsSummary` parser (#1194, Merged); resolved packet padding in `can_recv()` eliminating 100% CPU busy-loops (#1208). | ![Merged](https://img.shields.io/badge/PR_#1194-Merged-8957e5?style=flat-square&logo=git-merge) |
| **FoxIO JA4 Fingerprinting**<br/>`FoxIO-LLC/ja4`<br/>*(Official Industry Standard)* | [**PR #312**](https://github.com/FoxIO-LLC/ja4/pull/312)<br/>[**PR #314**](https://github.com/FoxIO-LLC/ja4/pull/314)<br/>[**PR #327**](https://github.com/FoxIO-LLC/ja4/pull/327) | **Zero-allocation HTTP/1 header filter & raw hex digest**: Eliminated heap allocations during HTTP/1 header filtering (#312); direct hex-encoded 6-byte raw digest slices in ja4/ja4x (#314); handled single-character ALPN per spec (#327). | ![3x Merged](https://img.shields.io/badge/Merged-3x_PRs-8957e5?style=flat-square&logo=git-merge) |
| **Foundry (Paradigm)**<br/>`foundry-rs/foundry`<br/>*(16,000+ ★)* | [**PR #16707**](https://github.com/foundry-rs/foundry/pull/16707) | **Chisel NTFS alternate data stream isolation**: Hardened session cache in `crates/chisel` against Windows NTFS Alternate Data Streams and path traversals, preventing arbitrary disk write escapes and cache contamination. | ![Merged](https://img.shields.io/badge/PR_#16707-Merged-8957e5?style=flat-square&logo=git-merge) |
| **Fly.io Corrosion**<br/>`superfly/corrosion`<br/>*(Distributed SQLite cluster)* | [**PR #559**](https://github.com/superfly/corrosion/pull/559)<br/>[**PR #578**](https://github.com/superfly/corrosion/pull/578) | **PostgreSQL wire AST rollback state recovery**: Implemented PostgreSQL wire protocol transaction abort state machine (`SQLSTATE 25P02`) and Extended Query sync recovery in corro-pg distributed SQLite. | ![Merged](https://img.shields.io/badge/PR_#559-Merged-8957e5?style=flat-square&logo=git-merge) |
| **Cloudflare Pingora**<br/>`cloudflare/pingora`<br/>*(22,000+ ★)* | [**PR #1000**](https://github.com/cloudflare/pingora/pull/1000)<br/>[**PR #996**](https://github.com/cloudflare/pingora/pull/996) | **Parser admission limits & RFC 9110 timeout mapping**: Engineered configurable HTTP/1 parser admission limits (#1000); mapped upstream connect, TLS handshake, and read/write timeouts to `504 Gateway Timeout` in `fail_to_proxy` (#996). | ![Reviewed](https://img.shields.io/badge/Reviewed-CI_100%25_Green-brightgreen?style=flat-square) |
| **Prebid Server**<br/>`prebid/prebid-server`<br/>*(AdTech Core Engine in Go)* | [**PR #5008**](https://github.com/prebid/prebid-server/pull/5008) | **PubMatic adapter index panic prevention**: Prevented out-of-range index panic in PubMatic banner size resolution during multi-format bid evaluation, with 94.1% statement test coverage. | ![Tested](https://img.shields.io/badge/PR_#5008-CI_Green-brightgreen?style=flat-square) |
| **Prebid Cache**<br/>`prebid/prebid-cache`<br/>*(High-throughput Go Cache)* | [**PR #224**](https://github.com/prebid/prebid-cache/pull/224) | **Configurable max HTTP body size control**: Implemented bounded `http.MaxBytesReader` body size limiter in routing handlers to prevent heap exhaustion attacks (#218). | ![Open](https://img.shields.io/badge/PR_#224-Open-blue?style=flat-square) |
| **Google Comprehensive Rust**<br/>`google/comprehensive-rust`<br/>*(28,000+ ★)* | [**PR #3275**](https://github.com/google/comprehensive-rust/pull/3275) | **LLVM Undefined Behavior modeling**: Accurately modeled language-level UB using intrinsic `i32::unchecked_add` in unsafe courseware modules per Google Staff Engineer design review. | ![Merged](https://img.shields.io/badge/PR_#3275-Merged-8957e5?style=flat-square&logo=git-merge) |
| **MaxMindDB**<br/>`oschwald/maxminddb-rust` | [**PR #120**](https://github.com/oschwald/maxminddb-rust/pull/120) | **Zero-allocation IP metadata lookup**: Accelerated GeoIP binary lookups using native big-endian byte decoding (`u32::from_be_bytes`), enabling single-CPU-instruction decoding of 32-bit database nodes. | ![Merged](https://img.shields.io/badge/PR_#120-Merged-8957e5?style=flat-square&logo=git-merge) |
| **SmartCore**<br/>`smartcorelib/smartcore` | [**PR #386**](https://github.com/smartcorelib/smartcore/pull/386) | **Pre-allocated capacity in ensemble trees**: Optimized ensemble tree training cycles by pre-allocating exact vector capacities in Random Forest models, eliminating repeated heap memory reallocations. | ![Merged](https://img.shields.io/badge/PR_#386-Merged-8957e5?style=flat-square&logo=git-merge) |
| **Kestra**<br/>`kestra-io/kestra`<br/>*(20,000+ ★)* | [**PR #20051**](https://github.com/kestra-io/kestra/pull/20051) | **Log viewer rendering stability**: Prevented layout shift on log body line clamp toggle across log viewer components. | ![Merged](https://img.shields.io/badge/PR_#20051-Merged-8957e5?style=flat-square&logo=git-merge) |
| **BranchBase**<br/>`oscarbol09/branchbase` | [**PR #126**](https://github.com/oscarbol09/branchbase/pull/126) | **Custom configuration CLI flag**: Added `--config / -c` flag to allow custom configuration file path resolution in BranchBase CLI (#114). | ![Merged](https://img.shields.io/badge/PR_#126-Merged-8957e5?style=flat-square&logo=git-merge) |
| **Astral uv**<br/>`astral-sh/uv`<br/>*(45,000+ ★)* | [**PR #21457**](https://github.com/astral-sh/uv/pull/21457) | **Cross-process file lock timeout propagation**: Decoupled lock acquisition from static timeouts by threading configurable timeout options through `EnvironmentOptions` across Astral's entire workspace toolchain. Passed all 55 CI matrix suites. | ![CI Green](https://img.shields.io/badge/CI_Green-55_Passed-brightgreen?style=flat-square) |
| **Turso libSQL**<br/>`tursodatabase/libsql`<br/>*(14,000+ ★)* | [**PR #2280**](https://github.com/tursodatabase/libsql/pull/2280) | **Default WAL journal mode for local databases**: Enforced Write-Ahead Logging (WAL) concurrency as default for local SQLite instances, preventing database locks under concurrent access. All 12 CI suites passed. | ![CI Green](https://img.shields.io/badge/CI_Green-12_Passed-brightgreen?style=flat-square) |

---

## 💻 Technical Toolbelt

```
Languages:        Rust (Tokio, Loom, Unsafe, Atomics, Zero-Copy Parsing), Go, C/C++, Python, SQL, Bash
Systems & Kernel: Linux Internals, eBPF/XDP Kernel Bypass, Sockets, Memory Safety, POSIX/WASI Filesystems
Networking:       TCP/IP, HTTP/1.1–HTTP/3, TLS 1.3, JA3/JA4 Fingerprinting, Reverse Proxies (Pingora, Envoy)
Concurrency:      Lock-Free Data Structures, Atomic CAS, Loom Concurrency CI, Thread Pooling, Epoll/Kqueue
Storage & State:  PostgreSQL, Redis, SQLite / libSQL (WAL Concurrency), Distributed Gossip State (Corrosion)
Observability:    Flamegraphs (perf), Prometheus Metrics, OpenTelemetry Tracing, k6 Multi-Core Load Testing
```

---

## 📬 Connect & Collaborate

- 🌐 **Personal Portfolio**: [aditya-9-6.github.io/Aditya_dahale-portfolio](https://aditya-9-6.github.io/Aditya_dahale-portfolio/)
- 📄 **1-Page Resume (PDF)**: [Download Verified Resume](https://aditya-9-6.github.io/Aditya_dahale-portfolio/Aditya_Dahale_Resume.pdf)
- 💼 **LinkedIn**: [linkedin.com/in/aditya-dahale-207208aditya](https://www.linkedin.com/in/aditya-dahale-207208aditya/)
- ✉️ **Email**: [adityadahale96@gmail.com](mailto:adityadahale96@gmail.com)

---

<div align="center">
  <sub>Built with low-latency precision & zero-allocation engineering.</sub>
</div>
