**Charles Liu**
Dr. Parteek Kumar
$10/22/2025$

___

### **Part 1**

___

### **Python CI Workflow**

![[Pasted image 20251022124702.png]]

___

### **Pytest Output**

![[Pasted image 20251022124626.png]]

___

### **Github Link**

https://github.com/CharlesLiuCool/python-ci-demo/settings

___

### **Part 2**

___


![[Pasted image 20251027122736.png]]

![[Pasted image 20251027125037.png]]
![[Pasted image 20251027125156.png]]

![[Pasted image 20251027125058.png]]

___

### **Reflection**

1. Explain the difference between Continuous Integration (CI) and Continuous  
Deployment (CD). How do these two practices work together to ensure reliable and efficient software delivery?  

CI is the practice of frequently merging code changes from multiple developers into a shared repository. Each of those merges causes automatic builds and tests to ensure that new code integrates smoothly and doesn't break existing stuff. CD extends CI by automatically deploying code to production after it passes all tests. Each time a code change meets quality standards it's release is automatic and immediate.

2. What is the purpose of the “checkout” step in a GitHub Actions workflow?  

This retrieves the repository's code onto the machine running where the workflow is executed. Without it, the runner wouldn't have access to source code, so build test and deploy wouldn't be able to operate.

3. What are GitHub-hosted runners, and how do they contribute to automation?  

They are VMs provided by Github to execute workflow jobs. They come preconfigured with tools and languages, and allow you to not have to set up your own infrastructure every time.

4. What challenges did you encounter while setting up or debugging your workflow, and what specific steps did you take to identify and resolve them?

The build would fail sometimes, and it took a few times of reading the build error. The docker token was not generated properly so I had to regenerate it.

5. How can you apply the skills and concepts learned from this CI/CD lab  
to your Software Engineering class project?

I can apply CI/CD to automate code quality detection and deployment processes, providing a clean workflow.

___