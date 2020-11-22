# ansible-openwrt
## Requirements
`opkg install python openssh-sftp-server`

## Variables
### Firewall
#### Redirect Rules
Following variables are located under `openwrt.firewall.redirect`
| Name                  | Type          | Description                           |
| --------------------- |:-------------:| ------------------------------------- |
| name                  | String (key)  | Name of firewall rule                 |
| src_zone              | String        | Source zone (default: wan)            |
| dst_zone              | String        | Destination zone (default: lan)       |
| dst_ip                | String        | Destination IP inside the zone        |
| src_ip                | String        | (OPTIONAL) Source IP                  |
| original_dst_port     | String        | Destination port that hit the firewall|
| dst_port              | String        | Destination port inside the zone      |
| proto                 | String        | Protocol (tcp/udp/...)                |
| enabled               | Bool          | Enable or disable rule (default: True)|

### Firewall Rules
Following variables are located under `openwrt.firewall.rule`
| Name                  | Type          | Description                           |
| --------------------- |:-------------:| ------------------------------------- |
| name                  | String (key)  | Name of firewall rule                 |
| src_zone              | String        | Source zone (default: wan)            |
| dst_zone              | String        | (OPTIONAL) Destination zone           |
| dst_ip                | List          | (OPTIONAL) Destination IP             |
| proto                 | List          | Protocol (tcp/udp/all/...)            |
| action                | String        | Action to do (ACCEPT/DROP)            |

### Zones Rules
Following variables are located under `openwrt.firewall.zone`
| Name                  | Type          | Description                           |
| --------------------- |:-------------:| ------------------------------------- |
| name                  | String (key)  | Name of zone                          |
| family                | String        | Zone IP family (default: ipv4)        |
| masquerade            | Bool          | (OPTIONAL) Enable masquerade on this zone|
| mtu_fix               | Bool          | (OPTIONAL) Enable MSS clamping        |
| network               | String        | Name of network                       |
| subnets               | List          | (OPTIONAL) List of subnet to match in this zone. When defined, do not use `network` |
| input                 | String        | Input action (ACCEPT/REJECT/DROP)     |
| output                | String        | Output action (ACCEPT/REJECT/DROP)    |
| forward               | String        | Forward action (ACCEPT/REJECT/DROP)   |
