 ┌────────────────────────────────────────────────────────┐
     │                   5G CORE NETWORK                      │
     │                                                        │
     │   [ OAM / TR-069 Server ]      [ Public Internet / CDN]│
     │              │                               │         │
     │     UPF (Session-AMBR: 40M)         UPF (Plan AMBR: 1G)│
     │              │                               │         │
     │     APN: jioairfibermu                  APN: jionet    │
     └──────────────┬───────────────────────────────┬─────────┘
                    │   5G Radio Interface (Uu)     │
                    │   Dual PDU Sessions           │
     ┌──────────────▼───────────────────────────────▼─────────┐
     │               ODCPE (Nokia AOD311NK - SDX62)           │
     │                                                        │
     │   Cellular Modems (rmnet_data0)      (rmnet_data1)     │
     │                │                          │            │
     │        VLAN Tag: 1999              VLAN: 0 / 100       │
     │                └────────────┬─────────────┘            │
     │                      Ethernet Switch                   │
     └─────────────────────────────┼──────────────────────────┘
                                   │ Gigabit Ethernet (PoE)
                                   │ 802.1Q Trunk
     ┌─────────────────────────────▼──────────────────────────┐
     │               INDOOR UNIT (Wi-Fi Router)               │
     │                                                        │
     │   • VLAN 1999 Interface ──> Internal TR-069 Client     │
     │   • VLAN 0 / 100 (WAN)  ──> Wi-Fi / LAN Clients (1Gbps)│
     └────────────────────────────────────────────────────────
