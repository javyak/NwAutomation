Check connectivity to all IP addresses configured in all network devices from all network devices. 

Plays:
- Clean up and create directiry - Cleaned up from previous collections
- Collect interface information from WAN Routers
Assumes all of them are IOS devices.
Uses ios_facts to get the configured IPv4 addresses and copies them into a file.
- Collect interface information from Spines and Leafs
Assumes all of them are EOS devices.
Uses eos_facts to get the configured IPv4 addresses and copies them into a file.
- Merge all interface information to a single file - just concatenate files for the next plays
- Test connectivity from WAN routers
Ping to all IP addresses discovered and expect a !!! output
- Test connectivity from Spines and Leafs (EOS)
Ping to all IP addresses discovered and expect a 5 received inside the messages[0] field

Future extension:
- Report failed pings into a file for helping with troubleshooting  