# Implemented a CI/CD pipeline using GitHub and AWs codepipeline to automatically deploy a static website to amazon s3.Integrated with AWs CloudFront as a CDN

STEP1 :Create a git repo add your index.html file push to your github

STEP2 :Create sw3 bucket ,uncheck all public access ,enable static website hosting

STEP3 :Make bucket public and add bucketpolicy

STEP4 :Create codepipeline ..

SOURCE STAGE :

SOURCE PROVIDER : Github .. connect to the github ,select repositaory where your sourcecode is available and slect branch..

BUILD STAGE : skip this 

DEPLOY STAGE : DEPLOY PROVIDER :amazon s3 and give extractfile yes ,and give your bucket name finally create pipeline ..

STEP5 : Create Cloudfront distribution ,IN oringin settings ->origin domain-> orin=gin type : give custom origin ,and protocol policy :HHTP only and settings dafault route object

STEP6 : update cloudfront cache ..After every deployment : #cloudfront ->invalidation  and cretae invalidation (/*) 

finaly access our website use cloudfront URL ..
