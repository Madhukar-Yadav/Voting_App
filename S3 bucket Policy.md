
# S3 bucket Policy

1. Place the 3 files into the S3 bucket created
2. Go to Permissions
    a. Select Bucket Policy
        i.  Add this json content in the text area
        ii. Save the policy.

```json
{    
	"Version": "2012-10-17",
	"Statement": 
    [		
        {		
            "Sid": "AddPerm",
            "Effect": "Allow",
            "Principal": "*",
		    "Action": "s3:GetObject",
		    "Resource": "arn:aws:s3:::samplevotingdemo/*"        
		}
		
    ]
}
``



/* Replace samplevotingdemo with your S3 bucket name */