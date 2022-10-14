# DNAC & Infoblox integration via API

This Postman API collection is built to pull IP pools from DNAC and push them into Infoblox IPAM.


It helps to avoid limitations of DNAC and Infoblox native integration.
More specifically - it doesn't require parent pool to be empty in Infoblox.


**It is assumed that Infoblox is also used as DHCP server. And is the only DHCP server in the environment.**


Collection workflow:
1. Collect all IP pools reserved for specified Site in DNAC
2. Convert DNAC response into proper format for Infoblox
3. Push converted data into Infoblox.

You can run all requests in the collection automatically for complete workflow.\

Or you can:
- Run DNAC folder first (responsible for steps 1 & 2 in workflow).
- Review converted data in "infoblox_ready_data" env. variable.
- And run Infoblox folder (responsible for step 3 of workflow).

---

INITIAL SETUP:

- Set mandatory collection variables.(Select DNAC & Infoblox collection and open Variables tab. Set proper values in both INITIAL and CURRENT VALUE fields):
  - "dnac_ip" - Specify DNAC IP or FQDN
  - "infoblox_ip" - Specify Infoblox IP or FQDN
  - "site_path" - Specify target DNAC Hierarchy Site in format: "Global/Area/Building".
- Specify DNAC credentials in DNAC/Authentication request. Authorization field.
- Specify Infoblox credentials in Infoblox/Authentication request. Authorization field.

---

Built for:\
DNAC 2.2.2.3 (API v1.0)\
Infoblox 8.4.4 (API v2.10)\
*API versions can be changed via collection variables*



