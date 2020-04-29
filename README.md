# hotspot

Configure DHCP server and setup a wifi hotspot on Raspberry pi.

## Requirements

None

## Role Variables

    hotspot_interface: <str>
    hotspot_domain_name: <str, root domain of the hotspot managed network>
    hotspot_domain_name_servers: <list, published name servers>
    hotspot_dhcp:
      first_ip: <str, first ip of the dhcp range>
      last_ip: <str, last ip of the dhcp range>
      address: <str, dhcp server ip address>
      subnet: <str, dhcp managed subnet network address>
      broadcast: <str, dhcp managed subnet network broadcast>
      mask: <str, dhcp managed subnet network mask>
      default_lease: <int, dhcp default lease time in seconds>
      max_lease: <int, dhcp maximum lease time in seconds>

    hotspot_wifi_ssid: <str, wifi hotspot SSID>
    hotspot_wifi_password: <str, wifi hotspot password>
    hotspot_wifi_channel: <int, wifi hotspot channel (ranges from 1-13)>

## Dependencies

- kill dhclient process manually (if it runs):
    - `ps waxu | grep -i dhclient`
    - `sudo kill $(pidof dhclient)`

## Example Playbook

    - hosts: servers
      roles:
         - role: ansible-role-hotspot

## License

None

## Author Information

Tomas Bellus
