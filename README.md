# Create Vlan on mikrotik and assign to aruba
## A. Mikrotik
1. Create VLAN for each SSID

ex: /interface vlan
add name=vlan2 vlan-id=2 interface=<Bridge_Interface_With_Internet>

/interface vlan
add name=vlan18 vlan-id=18 interface=dockers
add name=vlan19 vlan-id=19 interface=dockers
add name=vlan20 vlan-id=20 interface=dockers
add name=vlan21 vlan-id=21 interface=dockers
add name=vlan22 vlan-id=22 interface=dockers
add name=vlan23 vlan-id=23 interface=dockers
add name=vlan24 vlan-id=24 interface=dockers
add name=vlan25 vlan-id=25 interface=dockers
add name=vlan26 vlan-id=26 interface=dockers
add name=vlan27 vlan-id=27 interface=dockers
add name=vlan28 vlan-id=28 interface=dockers
add name=vlan29 vlan-id=29 interface=dockers
add name=vlan30 vlan-id=30 interface=dockers
add name=vlan31 vlan-id=31 interface=dockers
add name=vlan32 vlan-id=32 interface=dockers
add name=vlan33 vlan-id=33 interface=dockers

2. Add IP Pool to vlan
/ip address
add address=192.168.18.1/24 interface=vlan18
add address=192.168.19.1/24 interface=vlan19
add address=192.168.20.1/24 interface=vlan20
add address=192.168.21.1/24 interface=vlan21
add address=192.168.22.1/24 interface=vlan22
add address=192.168.23.1/24 interface=vlan23
add address=192.168.24.1/24 interface=vlan24
add address=192.168.25.1/24 interface=vlan25
add address=192.168.26.1/24 interface=vlan26
add address=192.168.27.1/24 interface=vlan27
add address=192.168.28.1/24 interface=vlan28
add address=192.168.29.1/24 interface=vlan29
add address=192.168.30.1/24 interface=vlan30
add address=192.168.31.1/24 interface=vlan31
add address=192.168.32.1/24 interface=vlan32
add address=192.168.33.1/24 interface=vlan33

3. Add DHCP servers for each VLAN:
** Create IP Pool
/ip pool add name=dhcp_v18 ranges=192.168.18.2-192.168.18.254
/ip pool add name=dhcp_v19 ranges=192.168.19.2-192.168.19.254
/ip pool add name=dhcp_v20 ranges=192.168.20.2-192.168.20.254
/ip pool add name=dhcp_v21 ranges=192.168.21.2-192.168.21.254
/ip pool add name=dhcp_v22 ranges=192.168.22.2-192.168.22.254
/ip pool add name=dhcp_v23 ranges=192.168.23.2-192.168.23.254
/ip pool add name=dhcp_v24 ranges=192.168.24.2-192.168.24.254
/ip pool add name=dhcp_v25 ranges=192.168.25.2-192.168.25.254
/ip pool add name=dhcp_v26 ranges=192.168.26.2-192.168.26.254
/ip pool add name=dhcp_v27 ranges=192.168.27.2-192.168.27.254
/ip pool add name=dhcp_v28 ranges=192.168.28.2-192.168.28.254
/ip pool add name=dhcp_v29 ranges=192.168.29.2-192.168.29.254
/ip pool add name=dhcp_v30 ranges=192.168.30.2-192.168.30.254
/ip pool add name=dhcp_v31 ranges=192.168.31.2-192.168.31.254
/ip pool add name=dhcp_v32 ranges=192.168.32.2-192.168.32.254
/ip pool add name=dhcp_v33 ranges=192.168.33.2-192.168.33.254

** Create Dhcp server
/ip dhcp-server add name=dhcp_a18 address-pool=dhcp_v18 interface=vlan18
/ip dhcp-server add name=dhcp_a19 address-pool=dhcp_v19 interface=vlan19  
/ip dhcp-server add name=dhcp_a20 address-pool=dhcp_v20 interface=vlan20 
/ip dhcp-server add name=dhcp_a21 address-pool=dhcp_v21 interface=vlan21 
/ip dhcp-server add name=dhcp_a22 address-pool=dhcp_v22 interface=vlan22 
/ip dhcp-server add name=dhcp_a23 address-pool=dhcp_v23 interface=vlan23
/ip dhcp-server add name=dhcp_a24 address-pool=dhcp_v24 interface=vlan24  
/ip dhcp-server add name=dhcp_a25 address-pool=dhcp_v25 interface=vlan25 
/ip dhcp-server add name=dhcp_a26 address-pool=dhcp_v26 interface=vlan26 
/ip dhcp-server add name=dhcp_a27 address-pool=dhcp_v27 interface=vlan27
/ip dhcp-server add name=dhcp_a28 address-pool=dhcp_v28 interface=vlan28
/ip dhcp-server add name=dhcp_a29 address-pool=dhcp_v29 interface=vlan29 
/ip dhcp-server add name=dhcp_a30 address-pool=dhcp_v30 interface=vlan30
/ip dhcp-server add name=dhcp_a31 address-pool=dhcp_v31 interface=vlan31 
/ip dhcp-server add name=dhcp_a32 address-pool=dhcp_v32 interface=vlan32
/ip dhcp-server add name=dhcp_a33 address-pool=dhcp_v33 interface=vlan33

** Create dhcp network
/ip dhcp-server network
add address=192.168.18.0/24 gateway=192.168.18.1
add address=192.168.19.0/24 gateway=192.168.19.1
add address=192.168.20.0/24 gateway=192.168.20.1
add address=192.168.21.0/24 gateway=192.168.21.1
add address=192.168.22.0/24 gateway=192.168.22.1
add address=192.168.23.0/24 gateway=192.168.23.1
add address=192.168.24.0/24 gateway=192.168.24.1
add address=192.168.25.0/24 gateway=192.168.25.1
add address=192.168.26.0/24 gateway=192.168.26.1
add address=192.168.27.0/24 gateway=192.168.27.1
add address=192.168.28.0/24 gateway=192.168.28.1
add address=192.168.29.0/24 gateway=192.168.29.1
add address=192.168.30.0/24 gateway=192.168.30.1
add address=192.168.31.0/24 gateway=192.168.31.1
add address=192.168.32.0/24 gateway=192.168.32.1
add address=192.168.33.0/24 gateway=192.168.33.1

4. Set Up Routing Rules
/ip firewall mangle
add chain=prerouting src-address=192.168.18.0/24 action=mark-routing new-routing-mark=h2-route1
add chain=prerouting src-address=192.168.19.0/24 action=mark-routing new-routing-mark=h2-route2
add chain=prerouting src-address=192.168.20.0/24 action=mark-routing new-routing-mark=h2-route3
add chain=prerouting src-address=192.168.21.0/24 action=mark-routing new-routing-mark=h2-route4
add chain=prerouting src-address=192.168.22.0/24 action=mark-routing new-routing-mark=h2-route5
add chain=prerouting src-address=192.168.23.0/24 action=mark-routing new-routing-mark=h2-route6
add chain=prerouting src-address=192.168.24.0/24 action=mark-routing new-routing-mark=h2-route7
add chain=prerouting src-address=192.168.25.0/24 action=mark-routing new-routing-mark=h2-route8
add chain=prerouting src-address=192.168.26.0/24 action=mark-routing new-routing-mark=h2-route9
add chain=prerouting src-address=192.168.27.0/24 action=mark-routing new-routing-mark=h2-route10
add chain=prerouting src-address=192.168.28.0/24 action=mark-routing new-routing-mark=h2-route11
add chain=prerouting src-address=192.168.29.0/24 action=mark-routing new-routing-mark=h2-route12
add chain=prerouting src-address=192.168.30.0/24 action=mark-routing new-routing-mark=h2-route13
add chain=prerouting src-address=192.168.31.0/24 action=mark-routing new-routing-mark=h2-route14
add chain=prerouting src-address=192.168.32.0/24 action=mark-routing new-routing-mark=h2-route15
add chain=prerouting src-address=192.168.33.0/24 action=mark-routing new-routing-mark=h2-route15






