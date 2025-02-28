---
title: Java VM Monitoring
parent: VM Monitoring
grand_parent: Monitoring
nav_order: 3
---

# **🚀 Application Monitoring Options**

## **1️⃣ Application Insights Java Agent (No Code Changes)**
This method involves attaching a **Java Agent** to the application at runtime, requiring **no source code modifications**.

### **🛠 How to Implement:**
- 📥 **Download the Java Agent**
- 🚀 **Start your application** with the agent using the following command:
  ```sh
  java -javaagent:applicationinsights-agent.jar -jar your-java-app.jar
  ```
- 🔑 **Set the instrumentation key** as an environment variable

### **✅ Pros:**
✔️ No modifications to the application code  
✔️ Automatically captures HTTP requests, database calls, exceptions, and JVM performance metrics  
✔️ Quick to set up and deploy  

### **⚠️ Cons:**
❌ Limited customization without additional configuration  
❌ Can introduce slight overhead due to auto-instrumentation  
❌ Some dependencies may not be automatically tracked  

### **⚡ Challenges:**
- Some frameworks may require additional setup for full visibility  
- There may be a minor performance impact depending on the application's workload  
- Ensure compatibility with your JVM version  

📖 **[Documentation: Application Insights Java Agent](#)**

---

## **2️⃣ OpenTelemetry SDK (Requires Code Changes)**
This option involves adding the **OpenTelemetry SDK** to the Java application for more control over what telemetry is collected.

### **🛠 How to Implement:**
- 📌 **Add OpenTelemetry dependencies** to the project  
- ✏️ **Modify the application code** to initialize telemetry and track specific events  
- 🚀 **Redeploy the application** with the changes  

### **✅ Pros:**
✔️ Fully customizable tracking for specific methods, database queries, and dependencies  
✔️ Provides deeper insights into business logic performance  
✔️ Works well for applications needing detailed metrics  

### **⚠️ Cons:**
❌ Requires modifying the application code and redeploying  
❌ Higher effort compared to the Java Agent  
❌ Additional dependencies need to be managed  

### **⚡ Challenges:**
- Every new metric or event requires additional development work  
- Configuration complexity increases compared to automatic monitoring  

📖 **[Documentation: OpenTelemetry Java SDK](#)**

---

## **3️⃣ Azure Monitor Agent on the VM (No Code Changes, System-Level Monitoring)**
This method enables **system-level monitoring** of the VM, such as **CPU, memory, and network performance**, without modifying the application.

### **🛠 How to Implement:**
- 🖥 **Enable the Azure Monitor Agent** on the VM through the Azure Portal  
- ⚙️ **Configure performance counters** for JVM monitoring  

### **✅ Pros:**
✔️ No changes required to the application or its runtime  
✔️ Helps diagnose infrastructure-level issues  
✔️ Useful for identifying VM performance bottlenecks  

### **⚠️ Cons:**
❌ Does not capture application-level metrics like request latency or database queries  
❌ Limited visibility into how the application interacts with dependencies  

### **⚡ Challenges:**
- Best used alongside another method that provides application-specific telemetry  
- Will not provide insights into request performance within the application  

📖 **[Documentation: Azure Monitor Agent Overview](#)**

---

## **🏆 Recommendation**
🔹 **For quick implementation with minimal effort** – Go with the **Java Agent**  
🔹 **For deep, customized application monitoring** – Use the **OpenTelemetry SDK**  
🔹 **For VM performance monitoring** – Enable the **Azure Monitor Agent**  