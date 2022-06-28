# Creating an Amazon SNS topic<a name="sns-create-topic"></a>

The first and most common Amazon SNS task is creating a topic\. This page shows how you can use the AWS Management Console, the AWS SDK for Java, and the AWS SDK for \.NET to create a topic\.

During creation, you choose a topic type \(standard or FIFO\) and name the topic\. After creating a topic, you can't change the topic type or name\. All other configuration choices are optional during topic creation, and you can edit them later\.

**Important**  
Do not add personally identifiable information \(PII\) or other confidential or sensitive information in topic names\. Topic names are accessible to other Amazon Web Services, including CloudWatch Logs\. Topic names are not intended to be used for private or sensitive data\.

**Topics**
+ [AWS Management Console](#create-topic-aws-console)
+ [AWS SDKs](#create-topic-aws-sdks)

## To create a topic using the AWS Management Console<a name="create-topic-aws-console"></a>

Aqui habla de como crear un Topic, pero son cosas que si vas a la consola las puedes recordar, solo dejé lo que si me pareció importante recordar. Otra cosa interesante sería el **Delivery retry policy** y **Delivery status logging**

1. \(Optional\) By default, only the topic owner can publish or subscribe to the topic\. To configure additional access permissions, expand the **Access policy** section\. For more information, see [Identity and access management in Amazon SNS](sns-authentication-and-access-control.md) and [Example cases for Amazon SNS access control](sns-access-policy-use-cases.md)\. 
**Note**  
When you create a topic using the console, the default policy uses the `aws:SourceOwner` condition key\. This key is similar to `aws:SourceAccount`\. 


## To create a topic using an AWS SDK<a name="create-topic-aws-sdks"></a>

To use an AWS SDK, you must configure it with your credentials\. For more information, see [The shared config and credentials files](https://docs.aws.amazon.com/sdkref/latest/guide/creds-config-files.html) in the *AWS SDKs and Tools Reference Guide*\.

The following code examples show how to create an Amazon SNS topic\.

------
#### [ \.NET ]

**AWS SDK for \.NET**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/dotnetv3/SNS#code-examples)\. 
  
+  For API details, see [CreateTopic](https://docs.aws.amazon.com/goto/DotNetSDKV3/sns-2010-03-31/CreateTopic) in *AWS SDK for \.NET API Reference*\. 

------
#### [ C\+\+ ]

**SDK for C\+\+**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/cpp/example_code/sns#code-examples)\. 

+  For API details, see [CreateTopic](https://docs.aws.amazon.com/goto/SdkForCpp/sns-2010-03-31/CreateTopic) in *AWS SDK for C\+\+ API Reference*\. 

------
#### [ Go ]

**SDK for Go V2**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/gov2/sns/CreateTopic#code-examples)\. 
+  For API details, see [CreateTopic](https://pkg.go.dev/github.com/aws/aws-sdk-go-v2/service/sns#Client.CreateTopic) in *AWS SDK for Go API Reference*\. 

------
#### [ Java ]

**SDK for Java 2\.x**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/javav2/example_code/sns#readme)\. 
  

```
    public static String createSNSTopic(SnsClient snsClient, String topicName ) {

        CreateTopicResponse result = null;
        try {
            CreateTopicRequest request = CreateTopicRequest.builder()
                    .name(topicName)
                    .build();

            result = snsClient.createTopic(request);
            return result.topicArn();
        } catch (SnsException e) {

            System.err.println(e.awsErrorDetails().errorMessage());
            System.exit(1);
        }
        return "";
    }
```
+  For API details, see [CreateTopic](https://docs.aws.amazon.com/goto/SdkForJavaV2/sns-2010-03-31/CreateTopic) in *AWS SDK for Java 2\.x API Reference*\. 

------
#### [ JavaScript ]

**SDK for JavaScript V3**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/javascriptv3/example_code/sns#code-examples)\. 
+  For more information, see [AWS SDK for JavaScript Developer Guide](https://docs.aws.amazon.com/sdk-for-javascript/v3/developer-guide/sns-examples-managing-topics.html#sns-examples-managing-topics-createtopic)\. 
+  For API details, see [CreateTopic](https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/clients/client-sns/classes/createtopiccommand.html) in *AWS SDK for JavaScript API Reference*\. 

------
#### [ Kotlin ]

**SDK for Kotlin**  
This is prerelease documentation for a feature in preview release\. It is subject to change\.
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/kotlin/services/sns#code-examples)\. 
  
+  For API details, see [CreateTopic](https://github.com/awslabs/aws-sdk-kotlin#generating-api-documentation) in *AWS SDK for Kotlin API reference*\. 

------
#### [ PHP ]

**SDK for PHP**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/php/example_code/sns#code-examples)\. 
+  For more information, see [AWS SDK for PHP Developer Guide](https://docs.aws.amazon.com/sdk-for-php/v3/developer-guide/sns-examples-managing-topics.html#create-a-topic)\. 
+  For API details, see [CreateTopic](https://docs.aws.amazon.com/goto/SdkForPHPV3/sns-2010-03-31/CreateTopic) in *AWS SDK for PHP API Reference*\. 

------
#### [ Python ]

**SDK for Python \(Boto3\)**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/python/example_code/sns#code-examples)\. 
+  For API details, see [CreateTopic](https://docs.aws.amazon.com/goto/boto3/sns-2010-03-31/CreateTopic) in *AWS SDK for Python \(Boto3\) API Reference*\. 

