This is simple reminder.
# rpi-vless-gateway-howto
One of solutions to struggle with Great Russian Firewall (Mikrotik+Raspberry Pi)

```
                                                         │                                   
                                        BGP              │     ┌────────────────────┐        
                                ┌────────────────────────┼─────┼ antizapret list    │        
                                │                        │     └────────────────────┘        
                                │                        │                                   
                                │                        │                                   
                                │                        │                  ....             
                                │                        │               ....  ...........   
                                │                        │            ....        ..      ...
                       ┌────────▼────┐      direct       │         ...  ..                  .
                       │ home router ┼───────────────────┼────────►        Internet         .
                       └───▲───┬─────┘                   │        ....        .....      ... 
                           │   │                         │           . ........   .......    
                           │   │gateway                  │ ┌────────────────┐        ▲       
                           │   │  ┌─────────────────┐    │ │    VPS         │        │       
┌─────────────┐            │   │  │   RPi           │    │ │  with sing-box ├────────┘       
│ home client ┼────────────┘   └─►│  with sing-box  │    │ │    server      │                
└─────────────┘                   │  client         │    │ └────────▲───────┘                
                                  └──────┬──────────┘    │          │                        
                                         │               │          │                        
                                         │               │          │                        
                                         └───────────────┼──────────┘                        
                                                   vless │                                   
                                                         │                                   
                                                         │                                   
                                          home net       │      Internet                     
                                                         └─                                  
```
Recommended equipment:
* router (ideally with openwrt support to integrate both routing and vless configurations in a single device)
* VPS (for VLESS server)

My equipment:
* router (Mikrotik, acts as default gateway and AP for home clients, manages routing to different resources, BGP route receiver)
* Raspberry Pi 4 (acts as a gateway for blocked resources, this route configured on Mikrotik)
* VPS with VLESS server

## Minimal router configuration (Mikrotik)
* Configure your WAN (WiFi, DHCP, clients, etc)

...TBD...
