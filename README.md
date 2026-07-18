# sovereign-edge-infrastructure
A production‑grade, decentralized edge orchestration system that unifies off‑grid bare‑metal servers into a secure, peer‑to‑peer compute mesh. Built for environments requiring autonomy, resilience, and zero cloud dependency.

# Architecture
* Lightweight Linux node agent written for hardware‑abstracted telemetry, security events, and workload hooks.

* Decentralized control plane coordinating node enrollment, trust zones, and cluster‑wide configuration.

* Zero‑trust overlay network using mTLS identity, rotating keys, and peer‑verified communication.

* Constraint‑aware scheduler optimized for unreliable connectivity, power‑limited nodes, and remote deployments.

* Next.js topology dashboard providing real‑time visualization of node layout, power budgets, bandwidth saturation, and throughput ratios.

# Features
* Bare‑metal provisioning — automated discovery, PXE‑style bootstrapping, and secure node registration.

* Hardware‑level firewall orchestration — centralized policy engine pushing per‑node rules.

* Local‑first resilience — workload failover, degraded‑mode operation, and offline recovery workflows.

* Real‑time telemetry — metrics streaming for CPU, power, network, trust state, and cluster health.
* Topology mapping — physical + logical cluster visualization with constraint overlays.

* Operator‑focused UX — clean dashboards for triage, configuration changes, and incident response.

| **Layer** | **Tech** | **Purpose** |
| --- | --- | --- |
| Node Agent | Rust / Go | Telemetry, security events, workload hooks |
| System Layer | Linux, systemd, nftables | Hardware abstraction, firewall control |
| Networking | mTLS, WireGuard, P2P mesh | Zero‑trust identity + encrypted communication |
| Orchestration | Custom scheduler | Local‑first failover + remote resilience |
| Control Plane | TypeScript, REST, WebSockets | Cluster config + real‑time metrics |
| Dashboard | Next.js, TailwindCSS, D3.js | Topology + constraint visualization |
| Data Layer | SQLite / RocksDB | Local caching + federated aggregation |
| Security | Key rotation, signed configs | Sovereign, tamper‑resistant infra |

flowchart TD

    subgraph EdgeCluster["Sovereign Edge Cluster"]
        A1["Node Agent<br/>Telemetry • Security • Workload Hooks"]
        A2["Local Scheduler<br/>Power‑Aware • Connectivity‑Aware"]
        A3["Zero‑Trust Mesh<br/>mTLS • WireGuard • Peer Identity"]
    end

    subgraph ControlPlane["Decentralized Control Plane"]
        B1["Config API<br/>REST • WebSockets"]
        B2["Metrics Ingest<br/>Real‑Time Streams"]
        B3["Policy Engine<br/>Firewall • Trust Zones"]
    end

    subgraph Dashboard["Operator Dashboard"]
        C1["Topology Map<br/>Nodes • Links • Regions"]
        C2["Constraint View<br/>Power • Bandwidth • Latency"]
        C3["Cluster Health<br/>Alerts • Logs • Status"]
    end

    A1 --> B2
    A2 --> B1
    A3 --> B3

    B1 --> C1
    B2 --> C2
    B3 --> C3
