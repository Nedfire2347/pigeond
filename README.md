# Ethernet Modem for IP Over Avian Carriers

Created for CMPT 433, and based loosely on RFC 1149.

## Components

### pigeond

Create a "pigeonN" network device using the tun/tap interface. Send and receive data over this device using the avian carrier link layer protocol. This should include a systemd unit file.

Currently we expect the network device to be configured outside our program. Once the program is running, run these commands, replacing "pigeon0" with the device that was created when the program started:

    sudo ip link set pigeon0 up
    sudo ip addr add 10.0.0.1/24 dev pigeon0

### pigeon-admin

NodeJS-based web server that displays status information and provides some tools to manage pigeond.

### Setup scripts

We need to do some initial configuration to bridge network interfaces. This is probably best done in a little shell script somewhere. We might be able to polish it up later.

## Authors

 * Adam Shambrook (ashambro@sfu.ca)
 * Dylan McCall (dmccall@sfu.ca)
 * Sunny Singh (psa71@sfu.ca)
