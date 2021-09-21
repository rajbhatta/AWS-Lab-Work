# Creating SSL Certificate for a domain #
<img src="img/img1.png"/>
<img src="img/img2.png"/>
<img src="img/img3.png"/>
<img src="img/img4.png"/>
<img src="img/img5.png"/>
<img src="img/img6.png"/>
<img src="img/img7.png"/>
<img src="img/img8.png"/>

## Adding CNAME to route 53 ##
<img src="img/img9.png"/>
<img src="img/img10.png"/>
<img src="img/img11.png"/>
<img src="img/img12.png"/>
<img src="img/img13.png"/>

## Configuring CloudFront for https and caching ##
- Create cloud front distribution 
<img src="img/img14.png"/>

- Copy URL of S3 bucket 
<img src="img/img15.png"/>

- Paste in Origin section 
<img src="img/img16.png"/>

- Select redirect to Https 
<img src="img/img17.png"/>

- Provide domain in alternate dname 
<img src="img/img18.png"/>

- Select certificate
<img src="img/img19.png"/>

- Enable distribution
<img src="img/img20.png"/>

- Test 

<b><p>Note: SSL certificate must be created in N. Verginia and email will be sent to email created for domain. If custom certificate is greyout, either certificate is not approved or created in another region.</b>
<br/>
<br/>

<img src="img/img21.png"/>

# Pointing our domain name to cloudfront https domain name #
- at this point we can access https using CloudFront domain name but still our domain name is lacking https.
- Thus, we need to point our domain name to cloudfront https domain name.

## Procedures to point domain name to HTTPSCLOUDFRONT DOMAIN NAME ##
- Goto route 53 and point record to cloudfront https domain because instead of s3 bucket url because cloudfront points to s3 bucket.

<img src="img/img22.PNG"/>
<img src="img/img23.PNG"/>
<img src="img/img24.PNG"/>
