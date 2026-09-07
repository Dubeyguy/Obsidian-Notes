# Domains and Sub domains

## Vertical and horizontal sub domain

- Horizontal: Includes all the different domains of that organization. Eg. All the different acquired domains or domains in different countries
- Vertical: Includes all the subdomains under that particular domain

![](Media/Pasted%20image%2020250121174554.png)

# Finding info about websites

- Arin whois: A website that lists the IP blocks and AS number
- bgp toolkit: Lists various metrics and analytics from an AS number
- mxtoolbox.com: For CIDR ranges and more
- Lopseg.com: A website containing most of tools for DNS purposes
- builtwith.com: Information about technologies used in a website and more back into the directory where all the files are located
- Hunter how: Like shodan but with maybe more features in free version

# Subdomain Enumeration

## Crt.sh: provides subdomains related to a website through the certificates issued to it

![](Media/Pasted%20image%2020250125190933.png)

## Virustotal

![](Media/Pasted%20image%2020250125191733.png)

## Chaos: Great way to find subdomains with horizontal sub domains too

![](Media/Pasted%20image%2020250125192811.png)

## Amass: Command line tool for finding subdomains

## Subfinder: Great tool for finding subdomains

## httpx: A brilliant tool for checking active subdomains, probe them and much more

## eyewitness: A great tool for screenshotting subdomains

## ffuf: Great tool for finding and bruteforcing subdomains using wordlists

![](Media/Pasted%20image%2020250303225944.png)

## dirsearch: for directory bruteforce

# Subdomain Takeover

## Key points

- CNAME: Canonical Name ( maps one domain to another without giving any ip address)
- can i take over - xyz (github repo listing vulnerable cloud services for subdomain takeover)
- dig (cli command to find dns records of subodmains)
- subzy (cli tool to find vulnerable subdomains for takeover)
- subjack (cli tool to find vulnerable subdomains for takeover)
- Nuclei (an all round tool for everything including takeovers)
