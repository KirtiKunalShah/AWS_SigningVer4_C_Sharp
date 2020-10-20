# AWS_SigningVer4_C_Sharp
C# .Net Implementation of AWS Version 4 Signing to successfully call AWS API's (execute-api)




It is essential to refer to error received from AWS (execute-api) as this has valuable information to tune the signing implementation 

-- Here is an error response from AWS --

{ "message": "The request signature we calculated does not match the signature you provided. Check your AWS Secret Access Key and signing method. Consult the service documentation for details.

The Canonical String for this request should have been
'POST
/live/api/delivery-agent/shipment

host:9sl8c9eseb.execute-api.us-east-1.amazonaws.com
x-amz-content-sha256:beaead3198f7da1e70d03ab969765e0821b24fc913697e929e726aeaebf0eba3
x-amz-date:20201020T061438Z
x-api-key:bDJ8R50GIQ8ZU9WB124kjaBrtXCngeZ34w5nVF4M

host;x-amz-content-sha256;x-amz-date;x-api-key
a4e670bb71ad8850db353502e49a389f479eabdf404c5371cdb1da709c584274'

The String-to-Sign should have been
'AWS4-HMAC-SHA256
20201020T061438Z
20201020/us-east-1/execute-api/aws4_request
25122330f43ed4b155d62a4e4882af5691455efb49591d8f9f827aa89267edff'
", "errorDetails": "" ,"method": POST, "path": /live/api/delivery-agent/shipment, "protocol": HTTP/1.1, "requestId": 74e28e63-131e-40d1-8dc6-b4d8bd05d815, "datetime": 20/Oct/2020:06:14:50 +0000 }


---   The Key items here are
1. a4e670bb71ad8850db353502e49a389f479eabdf404c5371cdb1da709c584274
2. 25122330f43ed4b155d62a4e4882af5691455efb49591d8f9f827aa89267edff

The correctness of these are important to achieve overall correctness of the Signature
