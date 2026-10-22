# Software-Security-Portfolio
A collection of secure software development projects and vulnerability assessments
# CS 305: Software Security
# Carlos Castellanos 

## Project Reflection: Artemis Financial

**Summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?**

Artemis Financial is a consulting company that develops individualized financial plans for customers. They sought to modernize their operations and required a software security audit of their public web interface. The primary issue was that their application lacked essential security controls. I was tasked with refactoring their software to implement data encryption in transit and cryptographic hashing to ensure data integrity and protect sensitive client information.

**What did you do well when you found your client's software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall well-being?**

I successfully identified the lack of secure communication protocols (HTTPS) and outdated dependencies. Coding securely is critical especially in the financial sector because it protects sensitive user data from being intercepted or manipulated. Implementing strong security adds immense value to a company by preserving its reputation, maintaining client trust, and ensuring compliance with financial data regulations, ultimately preventing catastrophic financial losses from breaches.

**Which part of the vulnerability assessment was challenging or helpful to you?**

Using the OWASP Dependency-Check scanner was incredibly helpful for automating the discovery of known vulnerabilities within the Spring Boot framework. However, configuring the Maven `pom.xml` to bypass the recent NVD API changes and successfully execute the scan was a challenging but highly educational aspect of the assessment. 

**How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?**

I increased layers of security by generating a custom keystore using Java Keytool and configuring the application to enforce HTTPS on port 8443, securing data in transit. I also implemented a SHA-256 cryptographic checksum to verify data integrity. In the future, I will continue using static application security testing (SAST) tools like OWASP Dependency-Check, combined with manual code reviews and threat modeling, to assess vulnerabilities and prioritize mitigations based on the severity of the threat.

**How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?**

I verified functionality by running the Spring Boot application locally in Eclipse and testing the secure `https://localhost:8443/hash` endpoint in a web browser to ensure the cipher executed correctly. To confirm no new vulnerabilities were introduced during refactoring, I re-ran the OWASP Dependency-Check Maven plugin on the updated codebase and reviewed the generated HTML report.

**What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?**

Key tools included the Java Keytool for certificate generation, Maven for dependency management and build automation, and the OWASP Dependency-Check plugin. The practice of iteratively testing the application after each refactoring step (e.g., verifying the cipher before deploying HTTPS) will be highly valuable in future backend development.

**Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?**

I would showcase the completed Practices for Secure Software Report and the refactored `SslServerApplication.java` file. This demonstrates my practical ability to implement industry-standard cryptographic algorithms (SHA-256), configure secure web servers, troubleshoot dependency management tools, and document my security practices professionally.
