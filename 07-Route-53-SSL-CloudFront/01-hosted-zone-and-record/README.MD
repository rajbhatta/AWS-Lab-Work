# 1. What is hosted zone in AWS #
- According to AWS, a hosted zone is analogous to a traditional DNS zone file; it represents a collection of records that can be managed together, belonging to a single parent domain name 

# 2. Type of record set and explanation in AWS #
## 2.1 A record type ##
- We use an A record to route traffic to a resource, such as a web server, using an IPv4 address in dotted decimal notation

## 2.2 AAAA record type ##

## 2.3 CNAME record type ##
- CNAME record, you can create an alias record at the top node of a DNS namespace, also known as the zone apex. For example, if you register the DNS name example.com, the zone apex is example.com. You can't create a CNAME record for example.com, but you can create an alias record for example.com that routes traffic to www.example.com (as long as www.example.com doesn't already have a CNAME record).

- Points to different URL which in turn can be resolved further by DNS.

## 2.4 MX record type ##

## 2.5 NS record type ##

## 2.6 SOA record tpe ##

## 2.7 TXT record type ##


## 2.8 PTR record type ##

## 2.9 SRC record type ##


## 2.10 SPF record type ##

## 2.11 NAPTR record type ##

## 2.12 CAA record type ##


# 3. What is ALIAS in record tpye #
- Amazon Route 53 alias records provide a Route 53–specific extension to DNS functionality. Alias records let you route traffic to selected AWS resources, such as CloudFront distributions and Amazon S3 buckets. They also let you route traffic from one record in a hosted zone to another record.

- When Route 53 receives a DNS query for an alias record, Route 53 responds with the applicable value for that resource:

1.1. An Amazon API Gateway custom regional API or edge-optimized API – Route 53 responds with one or more IP addresses for your API.

1.2. An Amazon VPC interface endpoint – Route 53 responds with one or more IP addresses for your interface endpoint.

1.3 A CloudFront distribution – Route 53 responds with one or more IP addresses for CloudFront edge servers that can serve your content.

1.4 An Elastic Beanstalk environment – Route 53 responds with one or more IP addresses for the environment.

1.5 An ELB load balancer – Route 53 responds with one or more IP addresses for the load balancer.

1.6 An AWS Global Accelerator accelerator – Route 53 responds with one of the two IP addresses for the accelerator.

1.7 An Amazon S3 bucket that is configured as a static website – Route 53 responds with one IP address for the Amazon S3 bucket.

1.8 Another Route 53 record in the same hosted zone – Route 53 responds as if the query is for the record that is referenced by the alias record.






