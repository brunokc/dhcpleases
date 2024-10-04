# dhcpleases

dhcpleases is a script that prints out DHCP leases to the terminal. It supports
dynamic and static leases using both IPv4 and IPv6 addresses. It works with 
ISC's dhcpd and dhcpd6 daemons.

## Command Line Options


```
> ./dhcpleases -h
dhcpleases [-a] [-i|-b|-e] [-d] [-m <oui_file>] [-4|-6]

    -a: output all leases, including expired ones.
    -i: sort output by IP address (default).
    -b: sort output by the start of the DHCP lease.
    -e: sort output by the end of the DHCP lease.
    -d: display only dynamic leases (ommit static ones).
    -m: use oui_file to resolve MAC addresses to names. By default file
        /usr/share/misc/oui.txt is used. oui_file can end with .txt or .json extensions.
    -4: output only IPv4 leases. By default both IPv4 and IPv6 are listed.
    -6: output only IPv6 leases. By default both IPv4 and IPv6 are listed.
```

## Example Output

IP and MAC addresses are masked in the output below.
 
```
> ./dhcpleases
IP              Lease Start          Lease End            MAC                Hostname        Manufacturer
--------------- -------------------- -------------------- ------------------ --------------- ------------------
10.1.1.24       <static>             <static>             xx:xx:xx:xx:xx:xx  denon           D&M Holdings Inc.
10.1.1.25       <static>             <static>             xx:xx:xx:xx:xx:xx  phillipshue     Philips Lighting BV
10.1.1.26       <static>             <static>             xx:xx:xx:xx:xx:xx  printer         CANON INC.
10.1.1.30       <static>             <static>             xx:xx:xx:xx:xx:xx  rpi             Raspberry Pi Trading Ltd
10.1.1.100      2024/10/03 16:08:40  2024/10/03 20:08:40  xx:xx:xx:xx:xx:xx  Sonos           Sonos, Inc.
10.1.1.104      2024/10/03 15:40:35  2024/10/03 19:40:35  xx:xx:xx:xx:xx:xx                  N/A
10.1.1.114      2024/10/03 17:14:14  2024/10/03 21:14:14  xx:xx:xx:xx:xx:xx                  Amazon Technologies Inc.
10.1.1.115      2024/10/03 17:01:56  2024/10/03 21:01:56  xx:xx:xx:xx:xx:xx                  N/A
10.1.1.123      2024/10/03 15:46:05  2024/10/03 19:46:05  xx:xx:xx:xx:xx:xx  iPhone          N/A
10.1.1.125      2024/10/03 17:06:50  2024/10/03 21:06:50  xx:xx:xx:xx:xx:xx                  Amazon Technologies Inc.
10.1.1.148      2024/10/03 17:11:18  2024/10/03 21:11:18  xx:xx:xx:xx:xx:xx  Legion          CLOUD NETWORK TECHNOLOGY SINGAPORE PTE. LTD.
10.1.1.153      2024/10/03 17:14:26  2024/10/03 21:14:26  xx:xx:xx:xx:xx:xx                  Amazon Technologies Inc.
10.1.1.162      2024/10/03 16:18:46  2024/10/03 20:18:46  xx:xx:xx:xx:xx:xx  XBOXONE         Microsoft Corporation
10.1.1.176      2024/10/03 15:44:44  2024/10/03 19:44:44  xx:xx:xx:xx:xx:xx  iPhone          N/A
10.1.1.184      2024/10/03 16:14:45  2024/10/03 20:14:45  xx:xx:xx:xx:xx:xx  LGwebOSTV       LG Electronics

Last Updated         Lease End            MAC                Hostname        Manufacturer
-------------------- -------------------- ------------------ --------------- -------------------------
fc00:1:408e:10::24
<static>             <static>             xx:xx:xx:xx:xx:xx  denon           D&M Holdings Inc.
fc00:1:408e:10::25
<static>             <static>             xx:xx:xx:xx:xx:xx  phillipshue     Philips Lighting BV
fc00:1:408e:10::26
<static>             <static>             xx:xx:xx:xx:xx:xx  printer         CANON INC.
fc00:1:408e:10::30
<static>             <static>             xx:xx:xx:xx:xx:xx  rpi             Raspberry Pi Trading Ltd
fc00:1:408e:10:8eff:13a3:98:3539
2024/10/03 11:50:40  2024/10/04 11:50:40  xx:xx:xx:xx:xx:xx                  N/A
fc00:1:408e:10:4055:14df:5300:d66c
2024/10/03 15:40:33  2024/10/04 15:40:33  xx:xx:xx:xx:xx:xx                  N/A
fc00:1:408e:10:481e:3dd9:e347:6faa
2024/10/02 18:25:18  2024/10/03 18:25:18  xx:xx:xx:xx:xx:xx  xboxone         Microsoft Corporation
fc00:1:408e:10:051b:596e:958e:65e
2024/10/02 23:26:44  2024/10/03 23:26:44  xx:xx:xx:xx:xx:xx                  N/A
fc00:1:408e:10:a7bc:71d7:4e34:5971
2024/10/03 15:44:45  2024/10/04 15:44:45  xx:xx:xx:xx:xx:xx                  N/A
fc00:1:408e:10:4f2d:e5fc:fc10:1f29
2024/10/03 17:11:10  2024/10/04 17:11:10  xx:xx:xx:xx:xx:xx  legion          LCFC(HeFei) Electronics Technology co., ltd
```
