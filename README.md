#Hack-secure-task
Intermediate pentesting tasks on http://testphp.vulnweb.com/: find open ports, brute-force hidden directories, capture login credentials with Wireshark, exploit SQL injection, and test for XSS vulnerabilities.

Internship Project Description
This project documents hands-on penetration testing on the intentionally vulnerable site http://testphp.vulnweb.com/ during my internship at Hack Secure (April–May 2025). The focus was to simulate real-world web attacks, identify critical security flaws, and provide actionable recommendations.

Key Activities
1. Port Scanning: Utilized Nmap to enumerate open ports and discover exposed network services.
2. Directory Enumeration: Applied Gobuster to uncover hidden paths like /admin, /cgi-bin, and sensitive files (credentials.txt, ipaddresses.txt, create.sql).
3. SQL Injection Testing: Leveraged SQLMap to extract database schemas and user credentials by exploiting injectable parameters in listproducts.php.
4. Cross-Site Scripting (XSS): Manually injected JavaScript payloads into search and guestbook fields to confirm XSS vulnerabilities.
5. Credential Hunting: Identified and validated leaked credentials for unauthorized access by analyzing exposed files and intercepted clear text transmissions.

Main Findings
Vulnerability	          Risk	        Example/Evidence
-------------------------------------------------------------------------------
1. Reflected XSS	        |  Critical	   | <script>alert('XSS')</script> in inputs
2. SQL Injection (SQLi) 	|  Critical	   | Extracted DB and credentials via SQLMap
3. Exposed Credentials	  |  High	       | credentials.txt/ipaddresses.txt discovered
4. Directory Listings	    |  Medium	     | /admin, /cgi-bin, create.sql exposed
5. Outdated Software	    |  Medium	     | nginx 1.19.0 and PHP 5.6.40 detected

Skills Demonstrated
1. Conducting vulnerability scanning (Nmap, SQLMap)
2. Directory and file brute-forcing (Gobuster)
3. Manual attack techniques (XSS payloads, SQLi)
4. Correlating and documenting vulnerability data
5. Communicating risk and mitigation strategies for stakeholders

Improvement Recommendations
1. Enforce input validation for all user inputs to prevent XSS and SQLi.
2. Restrict access to sensitive directories using IP whitelisting.
3. Implement regular patch management for server software.
