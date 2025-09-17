# Walking an Application — TryHackMe

**Objective:**  
Practice manual web application enumeration using only in-built browser tools (no automated scanners).  

---

## 🔑 Key Learnings

1. **HTML Comments**
   - Sensitive information may be left in HTML comments by developers.
   - Real-world example: credentials, API keys, or system notes.
   - **Interview Point:** Why should developers sanitize/remove comments before deployment?

2. **Hidden/Obscured Links**
   - Links hidden in source code or page elements can expose forgotten or sensitive functionality.
   - Example: admin panels, backup directories.
   - **Interview Point:** What are common ways attackers find hidden endpoints?

3. **Directory Listing**
   - Poor server configurations may allow directory browsing.
   - This can leak files like backups, configs, or credentials.
   - **Mitigation:** Disable directory listing on the server.
   - **Interview Point:** What misconfigurations are checked during web server hardening?

4. **Client-Side Restrictions (CSS/JS)**
   - Elements can be hidden via CSS (`display:none`) or manipulated by JavaScript.
   - Using **Inspector** and **Debugger**, attackers can bypass these client-side controls.
   - **Interview Point:** Why is client-side validation not enough for security?

5. **AJAX & Network Requests**
   - Forms and background requests often use AJAX to fetch/send data.
   - Observing the **Network tab** reveals hidden endpoints and request structures.
   - **Interview Point:** How can analyzing AJAX requests help in finding vulnerabilities?

---

## 🛠️ Tools & Techniques Used

- **View Source (`Ctrl+U`)**
  - Identified comments and hidden references.

- **Inspector (Developer Tools)**
  - Modified CSS properties to reveal hidden elements.
  - Viewed DOM structure for additional content.

- **Debugger**
  - Placed breakpoints in JavaScript.
  - Paused page execution to expose hidden content.

- **Network Tab**
  - Tracked AJAX requests during form submissions.
  - Identified how data flows between client and server.

---


## 🧠 Interview Preparation Notes

- Q: Why is manual application review important even with automated scanners available?  
- Q: What risks exist when sensitive information is left in HTML comments?  
- Q: How can browser developer tools be used in web application security testing?  
- Q: Why should server admins disable directory listing by default?  
- Q: What’s the risk of relying only on client-side validation?  

---

