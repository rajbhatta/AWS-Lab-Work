# 1. What is hosted zone in AWS #
- According to AWS, a hosted zone is analogous to a traditional DNS zone file; it represents a collection of records that can be managed together, belonging to a single parent domain name 

# 2. Type of record set and explanation in AWS #
## 2.1 A record type ##
- We use an A record to route traffic to a resource, such as a web server, using an IPv4 address in dotted decimal notation

## 2.2 AAAA record type ##
- AAAA record to route traffic to a resource, such as a web server, using an IPv6 address in colon-separated hexadecimal format.

## 2.3 CNAME record type ##
- CNAME record, you can create an alias record at the top node of a DNS namespace, also known as the zone apex. For example, if you register the DNS name example.com, the zone apex is example.com. You can't create a CNAME record for example.com, but you can create an alias record for example.com that routes traffic to www.example.com (as long as www.example.com doesn't already have a CNAME record).

- Points to different URL which in turn can be resolved further by DNS.

- A CNAME record can redirect DNS queries to any DNS record. For example, you can create a CNAME record that redirects queries from acme.example.com to zenith.example.com or to acme.example.org. You don't need to use Route 53 as the DNS service for the domain that you're redirecting queries to.

## 2.4 MX record type ##
- MX is a mail exchance record type that is related to DNS.

## 2.5 NS record type ##
- NS record identifies the name servers for the hosted zone. The name servers are provided with each domain by domain provider.

## 2.6 SOA record tpe ##
- It indentifies the base DNS information about the domain, for example: ns-2048.awsdns-64.net. hostmaster.example.com.

## 2.7 TXT record type ##
- A TXT record (short for text record) is a type of resource record in the Domain name system (DNS) used to provide the ability to associate arbitrary text with a host or other name, such as human readable information about a server, network, data center, or other accounting information.

```js
host.widgets.com.   IN   TXT   "printer=lpr5"
```

## 2.8 PTR record type ##
While DNS A records are stored under the given domain name, DNS PTR records are stored under the IP address — reversed, and with ".in-addr.arpa" added. 

```js
For example, the PTR record for the IP address 192.0.2.255 would be stored under "255.2.0.192.in-addr.arpa".
```

## 2.9 SRC record type ##


## 2.10 SPF record type ##

## 2.11 NAPTR record type ##

## 2.12 CAA record type ##


# 3. What is ALIAS in record tpye #
1. Amazon Route 53 alias records provide a Route 53–specific extension to DNS functionality. Alias records let you route traffic to selected AWS resources, such as CloudFront distributions and Amazon S3 buckets. They also let you route traffic from one record in a hosted zone to another record.

2. When Route 53 receives a DNS query for an alias record, Route 53 responds with the applicable value for that resource:

- <b>2.1. An Amazon API Gateway custom regional API or edge-optimized API</b> – Route 53 responds with one or more IP addresses for your API.

- <b>2.2. An Amazon VPC interface endpoint </b> – Route 53 responds with one or more IP addresses for your interface endpoint.

- <b>2.3 A CloudFront distribution </b> – Route 53 responds with one or more IP addresses for CloudFront edge servers that can serve your content.

- <b>2.4 An Elastic Beanstalk environment </b> – Route 53 responds with one or more IP addresses for the environment.

- <b>2.5 An ELB load balancer </b> – Route 53 responds with one or more IP addresses for the load balancer.

- <b>2.6 An AWS Global Accelerator accelerator  </b>– Route 53 responds with one of the two IP addresses for the accelerator.

- <b> 2.7 An Amazon S3 bucket that is configured as a static website </b> – Route 53 responds with one IP address for the Amazon S3 bucket.

- <b>2.8 Another Route 53 record in the same hosted zone </b> – Route 53 responds as if the query is for the record that is referenced by the alias record.

3. An alias record can only redirect queries to selected AWS resources, such as the following:

- <b>Amazon S3 buckets</b>

- <b>CloudFront distributions</b>

- <b>Another record in the same Route 53 hosted zone </b>

- For example, you can create an alias record named acme.example.com that redirects queries to an Amazon S3 bucket that is also named acme.example.com. You can also create an acme.example.com alias record that redirects queries to a record named zenith.example.com in the example.com hosted zone.

## 3.1 Reference ##
- https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resource-record-sets-choosing-alias-non-alias.html







