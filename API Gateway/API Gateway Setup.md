# API Gateway Setup

1. Create resource with CORS
2. Create POST endpoint
    a. Integrate with lambda
        i. Add body mapping template for application/x-www-form-urlencoded:

```json
        {
                "httpMethod": "POST",
                "body": {
                    #foreach( $token in $input.path('$').split('&') )
                        #set( $keyVal = $token.split('=') )
                        #set( $keyValSize = $keyVal.size() )
                        #if( $keyValSize >= 1 )
                            #set( $key = $util.urlDecode($keyVal[0]) )
                            #if( $keyValSize >= 2 )
                                #set( $val = $util.urlDecode($keyVal[1]) )
                            #else
                                #set( $val = '' )
                            #end
                            "$key": "$val"#if($foreach.hasNext),#end
                        #end
                    #end
                }
        }
```


    b. Modify Method Response / Integration Response to return 204 status code

    