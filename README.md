# CS-305-8-1-Journal

Briefly summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?

Artemis Financial is a consulting firm that manages sensitive stuff like savings and retirement plans. Since they deal with people's livelihoods, securing their communications is the absolute foundation of their clients' trust. My job was to help them navigate global data privacy laws and domestic financial regulations by securing their RESTful web API and updating their open-source libraries to prevent attackers from exploiting known vulnerabilities.

What did you do well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall well-being?

I did a great job manually reviewing the codebase and using static testing to find major issues, like a severely outdated Bouncy Castle cryptography library and an old Java 1.8 runtime. Secure coding is critical here because if financial data gets intercepted, the financial and reputational damage to the company would be devastating. Good security adds value by keeping Artemis compliant and maintaining their clients' trust.

 Which part of the vulnerability assessment was challenging or helpful to you?

The OWASP dependency-check tool was incredibly helpful because it flagged specific CVEs straight from the National Vulnerability Database. It easily caught severe vulnerabilities in our Bouncy Castle and Spring Framework versions. The most challenging part was realizing we were missing core security dependencies entirely, like spring boot starter security, which left our API endpoints completely exposed to the public.  

How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?

I mapped out a mitigation plan to patch the cryptography library to version 1.60 and upgrade the Spring Framework to close directory traversal loopholes. I also planned to integrate spring-boot-starter-security for authentication and strictly enforce HTTPS/TLS. In the future, I'd keep the OWASP dependency-check active in our automated build process so that if someone introduces a bad library, the build fails before hitting production.

How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?

To keep things functional but secure, I made sure all user input was sanitized before it touched the database by adding constraints to our API endpoints. After updating the code, checking for new vulnerabilities is as simple as relying on that automated OWASP dependency-check during the build process.  

What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?

The OWASP dependency-check tool and the National Vulnerability Database were definitely my top resources. For coding practices, I'll absolutely carry forward the habits of actively updating open-source libraries, sanitizing all input, and enforcing HTTPS with zero exceptions for plaintext.  

Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?

I'd show them this Vulnerability Assessment Report. It proves I know how to manually inspect a codebase for outdated frameworks, use static testing to find specific CVE codes, and create a solid mitigation plan to fix things like missing input validation and outdated encryption.  
