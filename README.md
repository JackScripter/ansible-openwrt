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
| enabled               | Bool          | (OPTIONAL) Enable or disable rule (default: True)|
