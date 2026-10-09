# DNS Walkthrough: How the Internet Connects Us

Have you ever wondered how typing `google.com` or `yourname.netlify.app` magically brings up a website? It all works thanks to DNS, and here is a plain-words explanation of how that hidden infrastructure actually works.

## What is DNS?
DNS stands for **Domain Name System**. You can think of it as the "Phonebook of the Internet." 
Computers don't understand words like "google.com"; they only understand numbers called IP addresses (like `192.168.1.1` or `203.0.113.55`). DNS is the system that translates the human-readable domain names we type into the IP addresses that computers need to locate each other.

## The Journey: From Typing an Address to Loading the Page
When someone types my website URL into their browser, a 4-step invisible relay race happens in milliseconds:

1. **The Resolver:** My browser first checks if it already knows the IP address. If it doesn't, it asks my internet provider's "DNS Resolver." The resolver's only job is to hunt down the IP address for me.
2. **The Root & TLD Nameservers:** The resolver asks the Root Server, which says, "I don't know the exact address, but I know who handles all `.app` domains." It points the resolver to the Top-Level Domain (TLD) Nameserver.
3. **The Authoritative Nameserver:** The TLD server points the resolver to the final boss: the Authoritative Nameserver. This server holds the actual, official record for my specific website. 
4. **The Response:** The Authoritative Nameserver hands the exact IP address back to the resolver, which passes it to my browser. Finally, my browser uses that IP address to connect directly to the host (like Netlify or Cloudflare) and download the webpage!

## What is a CNAME Record?
When setting up a custom domain (like `www.deepakprajapati.com`), we use a **CNAME (Canonical Name)** record.

A CNAME record doesn't point to an IP address (numbers); it points to *another domain name* (words). It acts like an alias or a forwarding address. 
For example, if my Netlify site is hosted at `deepak-portfolio.netlify.app`, I can create a CNAME record that tells the internet: *"If anyone asks for `www.deepakprajapati.com`, just forward them to `deepak-portfolio.netlify.app`."* 

This is incredibly useful because if Netlify ever changes their underlying IP address, I don't have to update anything. My CNAME record just safely points to the Netlify domain, and Netlify handles the rest.
