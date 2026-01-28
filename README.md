
A Groovy RCE payload that writes a JSP bind shell into the web application root.
This is useful in environments where outbound connections are restricted and reverse shells are not feasible (e.g., strict egress firewalling).

**Example use case:**

> Initial access is limited to a Groovy script console, and outbound network connections are blocked, preventing reverse shell callbacks.
> This technique demonstrates how to pivot to an inbound bind shell instead.

I published a detailed PoC explaining the why and how here:
[https://vipa0z.github.io/2025/10/22/abusing-groovy-script-consoles/](https://vipa0z.github.io/2025/10/22/abusing-groovy-script-consoles/)

**Usage**

1. Modify paths to match the target web application deployment directory.
2. Execute the Groovy script to drop the JSP bind shell on disk.
3. Trigger the bind shell by requesting the JSP endpoint:

   ```bash
   curl https://target/bindshell.jsp
   ```

---

