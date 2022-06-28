# Configuring Amazon SNS topic tags<a name="sns-tags-configuring"></a>

**Important**  
Do not add personally identifiable information \(PII\) or other confidential or sensitive information in tags\. Tags are accessible to other Amazon Web Services, including billing\. Tags are not intended to be used for private or sensitive data\.

**Topics**
+ [Adding tags to a topic using an AWS SDK](#tag-resource-aws-sdks)
+ [Managing tags with Amazon SNS API actions](#manage-tags-with-sns-api-actions)
+ [API actions that support ABAC](#api-actions-that-support-abac)

## Adding tags to a topic using an AWS SDK<a name="tag-resource-aws-sdks"></a>

------
#### [ Java ]

**SDK for Java 2\.x**  
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/javav2/example_code/sns#readme)\. 
  

```
    public static void addTopicTags(SnsClient snsClient, String topicArn) {

     try {
        Tag tag = Tag.builder()
                .key("Team")
                .value("Development")
                .build();

        Tag tag2 = Tag.builder()
                .key("Environment")
                .value("Gamma")
                .build();

        List<Tag> tagList = new ArrayList<>();
        tagList.add(tag);
        tagList.add(tag2);

        TagResourceRequest tagResourceRequest = TagResourceRequest.builder()
                .resourceArn(topicArn)
                .tags(tagList)
                .build();

        snsClient.tagResource(tagResourceRequest);
        System.out.println("Tags have been added to "+topicArn);

      } catch (SnsException e) {
          System.err.println(e.awsErrorDetails().errorMessage());
          System.exit(1);
      }
   }
```
+  For API details, see [TagResource](https://docs.aws.amazon.com/goto/SdkForJavaV2/sns-2010-03-31/TagResource) in *AWS SDK for Java 2\.x API Reference*\. 

------
#### [ Kotlin ]

**SDK for Kotlin**  
This is prerelease documentation for a feature in preview release\. It is subject to change\.
 To learn how to set up and run this example, see [GitHub](https://github.com/awsdocs/aws-doc-sdk-examples/tree/main/kotlin/services/sns#code-examples)\. 
+  For API details, see [TagResource](https://github.com/awslabs/aws-sdk-kotlin#generating-api-documentation) in *AWS SDK for Kotlin API reference*\. 

------

## Managing tags with Amazon SNS API actions<a name="manage-tags-with-sns-api-actions"></a>

To manage tags using the Amazon SNS API, use the following API actions:
+ [https://docs.aws.amazon.com/sns/latest/api/API_ListTagsForResource.html](https://docs.aws.amazon.com/sns/latest/api/API_ListTagsForResource.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_TagResource.html](https://docs.aws.amazon.com/sns/latest/api/API_TagResource.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_UntagResource.html](https://docs.aws.amazon.com/sns/latest/api/API_UntagResource.html)

## API actions that support ABAC<a name="api-actions-that-support-abac"></a>

The following is a list of API actions that support attribute\-based access control \(ABAC\)\. For more details about ABAC, see [What is ABAC for AWS?](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_attribute-based-access-control.html) in the *IAM User Guide*\.
+ [https://docs.aws.amazon.com/sns/latest/api/API_AddPermission.html](https://docs.aws.amazon.com/sns/latest/api/API_AddPermission.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_ConfirmSubscription.html](https://docs.aws.amazon.com/sns/latest/api/API_ConfirmSubscription.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_DeleteTopic.html](https://docs.aws.amazon.com/sns/latest/api/API_DeleteTopic.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_GetSubscriptionAttributes.html](https://docs.aws.amazon.com/sns/latest/api/API_GetSubscriptionAttributes.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_GetTopicAttributes.html](https://docs.aws.amazon.com/sns/latest/api/API_GetTopicAttributes.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_ListSubscriptionsByTopic.html](https://docs.aws.amazon.com/sns/latest/api/API_ListSubscriptionsByTopic.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_ListTagsForResource.html](https://docs.aws.amazon.com/sns/latest/api/API_ListTagsForResource.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_Publish.html](https://docs.aws.amazon.com/sns/latest/api/API_Publish.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_PublishBatch.html](https://docs.aws.amazon.com/sns/latest/api/API_PublishBatch.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_RemovePermission.html](https://docs.aws.amazon.com/sns/latest/api/API_RemovePermission.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_SetSubscriptionAttributes.html](https://docs.aws.amazon.com/sns/latest/api/API_SetSubscriptionAttributes.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_SetTopicAttributes.html](https://docs.aws.amazon.com/sns/latest/api/API_SetTopicAttributes.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_Subscribe.html](https://docs.aws.amazon.com/sns/latest/api/API_Subscribe.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_TagResource.html](https://docs.aws.amazon.com/sns/latest/api/API_TagResource.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_Unsubscribe.html](https://docs.aws.amazon.com/sns/latest/api/API_Unsubscribe.html)
+ [https://docs.aws.amazon.com/sns/latest/api/API_UntagResource.html](https://docs.aws.amazon.com/sns/latest/api/API_UntagResource.html)
