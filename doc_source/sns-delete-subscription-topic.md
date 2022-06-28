# Deleting an Amazon SNS subscription and topic<a name="sns-delete-subscription-topic"></a>

## To delete a subscription and topic using an AWS SDK<a name="delete-topic-aws-sdks"></a>

------
#### [ \.NET ]

**AWS SDK for \.NET**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/dotnetv3/SNS#code-examples)\. 
+  For API details, see [DeleteTopic](https://docs.aws.amazon.com/goto/DotNetSDKV3/sns-2010-03-31/DeleteTopic) in *AWS SDK for \.NET API Reference*\. 

------
#### [ C\+\+ ]

**SDK for C\+\+**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/cpp/example_code/sns#code-examples)\. 
+  For API details, see [DeleteTopic](https://docs.aws.amazon.com/goto/SdkForCpp/sns-2010-03-31/DeleteTopic) in *AWS SDK for C\+\+ API Reference*\. 

------
#### [ Java ]

**SDK for Java 2\.x**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/javav2/example_code/sns#readme)\. 
  

```
    public static void deleteSNSTopic(SnsClient snsClient, String topicArn ) {

        try {
            DeleteTopicRequest request = DeleteTopicRequest.builder()
                .topicArn(topicArn)
                .build();

            DeleteTopicResponse result = snsClient.deleteTopic(request);
            System.out.println("\n\nStatus was " + result.sdkHttpResponse().statusCode());

        } catch (SnsException e) {
            System.err.println(e.awsErrorDetails().errorMessage());
            System.exit(1);
        }
    }
```
+  For API details, see [DeleteTopic](https://docs.aws.amazon.com/goto/SdkForJavaV2/sns-2010-03-31/DeleteTopic) in *AWS SDK for Java 2\.x API Reference*\. 

------
#### [ JavaScript ]

**SDK for JavaScript V3**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/javascriptv3/example_code/sns#code-examples)\. 
+  For more information, see [AWS SDK for JavaScript Developer Guide](https://docs.aws.amazon.com/sdk-for-javascript/v3/developer-guide/sns-examples-managing-topics.html#sns-examples-managing-topics-deletetopic)\. 
+  For API details, see [DeleteTopic](https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/clients/client-sns/classes/deletetopiccommand.html) in *AWS SDK for JavaScript API Reference*\. 

------
#### [ Kotlin ]

**SDK for Kotlin**  
This is prerelease documentation for a feature in preview release\. It is subject to change\.
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/kotlin/services/sns#code-examples)\. 
+  For API details, see [DeleteTopic](https://github.com/awslabs/aws-sdk-kotlin#generating-api-documentation) in *AWS SDK for Kotlin API reference*\. 

------
#### [ PHP ]

**SDK for PHP**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/php/example_code/sns#code-examples)\. 
+  For API details, see [DeleteTopic](https://docs.aws.amazon.com/goto/SdkForPHPV3/sns-2010-03-31/DeleteTopic) in *AWS SDK for PHP API Reference*\. 

------
#### [ Python ]

**SDK for Python \(Boto3\)**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/python/example_code/sns#code-examples)\. 
+  For API details, see [DeleteTopic](https://docs.aws.amazon.com/goto/boto3/sns-2010-03-31/DeleteTopic) in *AWS SDK for Python \(Boto3\) API Reference*\. 

------
