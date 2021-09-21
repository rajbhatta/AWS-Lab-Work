# 1. Create S3 bucket #
- If we are going to redirect domain to s3 bucket then first then we need to do is to create s3 bucket.
- <b> Note: S3 bucket name must be created similar to the domain name </b>


# 2. Procedures for creating a S3 bucket and redirect from bucket #
<img src="img/img1.png"/>
<img src="img/img2.png"/>
<img src="img/img3.png"/>
<img src="img/img4.png"/>
<img src="img/img5.png"/>

## 2.1 Redirect to another domain from bucket ##
<img src="img/img6.png"/>

# 3. Create hosted zone #
<img src="img/img7.png"/>
<img src="img/img8.png"/>

# 4. Configure NS server inside GoDaddy or domain #
<img src="img/img9.png"/>

- <h3> <b>You must wait for NS server configuration from domain provider for at least 3 hours</b> </h3>

# 4. Create record and point to S3 bucket #
<img src="img/img10.png"/>
<img src="img/img11.png"/>
<img src="img/img12.png"/>
<img src="img/img13.png"/>
<img src="img/img14.png"/>
<img src="img/img15.png"/>
