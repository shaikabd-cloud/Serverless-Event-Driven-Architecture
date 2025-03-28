# Serverless-Event-Driven-Architecture
Building an Event-Driven Architecture with AWS S3, Lambda, and SNS Integration

---

### **Building an Event-Driven Architecture with S3, Lambda, and SNS Integration**

#### **Project Flow Overview:**

1. **User uploads an image to S3:** This triggers an **S3 Object Created** event.
2. **Lambda processes the event:** It extracts details like the bucket name and file key.
3. **Lambda publishes a notification to SNS:** The notification contains information about the uploaded image.
4. **SNS sends notifications to subscribers:** Subscribers (email/SMS) are notified when a new image is uploaded.


#### **Project Architecture:**
![image](https://github.com/user-attachments/assets/e4327de3-3d0c-484a-9499-20d8f2d0f236)

**AWS Services Used**:  
- **Amazon S3**: To store images uploaded by users.  
- **AWS Lambda**: To process events triggered by S3 uploads.  
- **Amazon SNS**: To notify subscribers about new uploads.

Here’s a simple illustration of the architecture:

- **S3 (Storage Service)**: Stores images uploaded by the user.
- **Lambda (Serverless Function)**: Processes the event generated by S3 when a new file is uploaded.
- **SNS (Notification Service)**: Sends notifications (via email/SMS) to the subscribers about the new image upload.

#### **Step-by-Step Guide:**

1. **Set up an S3 Bucket**:  
   - Create an S3 bucket to store the images.
  
2. **Create an SNS Topic**:  
   - Create an SNS Topic.
   - Subscribe to the topic (e.g., using email).
  
3. **Create a Lambda Function**:  
   - Write a Lambda function (`ImageUploadProcessor`) to process the S3 event and publish a message to SNS.
   - Use **Python** for the Lambda runtime (Python 3.9).
  
4. **Add Trigger for S3 Events**:  
   - Add an S3 trigger to invoke the Lambda function whenever a new image is uploaded to the S3 bucket.
  
5. **Write the Lambda Function Code**:  
   - The function extracts bucket name and key from the S3 event and publishes a message to the SNS topic.

6. **Test the Setup**:  
   - Upload an image to the S3 bucket. The Lambda function is triggered, and an email notification is sent via SNS.

---

### **Key Features and Technologies:**

- **Serverless Architecture**: No servers to manage! AWS Lambda handles everything.
- **Scalable and Cost-Effective**: With S3 and SNS, this solution scales automatically as your app grows.
- **Real-time Notifications**: Subscribers are notified instantly when a new image is uploaded.

### **Expected Outcome:**
By the end of this project, you’ll have built a fully functional **Event-Driven Architecture** using **AWS Lambda**, **S3**, and **SNS**. This will give you hands-on experience in working with AWS services and handling real-time events in a cloud-native application.

---
