### Retrieve lost password for Jenkins credential  
Run script in console:  

```
import com.cloudbees.plugins.credentials.CredentialsProvider
import com.cloudbees.plugins.credentials.common.StandardUsernamePasswordCredentials
import jenkins.model.Jenkins
import hudson.security.ACL

String credentialId = 'name_of_credential_here' // Replace with your credential ID

Jenkins jenkins = Jenkins.getInstance()

List<StandardUsernamePasswordCredentials> credentials = CredentialsProvider.lookupCredentials(
    StandardUsernamePasswordCredentials.class, jenkins, ACL.SYSTEM, Collections.emptyList()
)

StandardUsernamePasswordCredentials credential = credentials.find { it.id == credentialId }

if (credential) {
    String password = new String(credential.password.getPlainText())
    println("Username: ${credential.username}")
    println("Password: $password") // Be cautious with this line
} else {
    println("Credential not found")
}
```
