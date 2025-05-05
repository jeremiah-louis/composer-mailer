# PHPMailer Email Sending Script

This project demonstrates how to send emails using the **PHPMailer** library in PHP. It uses the **`vlucas/phpdotenv`** package to securely manage sensitive information like SMTP credentials through environment variables.

---

## Prerequisites

Before running this script, ensure you have the following installed:

1. **PHP** (version 7.4 or higher recommended)
2. **Composer** (PHP dependency manager)
3. An SMTP server (e.g., Gmail, Yahoo, or any other email provider)

---

## Setup Instructions

### 1. Clone or Download the Project
Clone the repository or download the project files to your local machine.

```bash
git clone <repository-url>
cd composer-mailer
```

---

### 2. Install Dependencies
Install the required PHP libraries using Composer:

```bash
composer install
```

This will install the following dependencies:
- **PHPMailer**: For sending emails.
- **vlucas/phpdotenv**: For managing environment variables.

---

### 3. Create a [`.env`](.env ) File
Create a [`.env`](.env ) file in the root directory of the project to store your SMTP credentials and other sensitive information. Below is an example of what the [`.env`](.env ) file should look like:

```env
SMTP_HOST=smtp.example.com
SMTP_USERNAME=your-email@example.com
SMTP_PASSWORD=your-email-password
SMTP_PORT=465
SMTP_FROM_EMAIL=your-email@example.com
SMTP_FROM_NAME=Your Name
```

#### Notes:
- Replace `smtp.example.com` with your SMTP server (e.g., `smtp.gmail.com` for Gmail).
- Replace `your-email@example.com` and `your-email-password` with your email credentials.
- If using Gmail, you may need to enable **App Passwords** or allow "Less Secure Apps" in your Google account settings.

---

### 4. Update [`.gitignore`](.gitignore )
Ensure the [`.env`](.env ) file is added to [`.gitignore`](.gitignore ) to prevent it from being committed to version control:

```gitignore
# Ignore .env file
.env
```

---

### 5. Run the Script
Run the script using the PHP CLI:

```bash
php test_email.php
```

If everything is set up correctly, you should see the following message:
```
Test email has been sent successfully.
```

If there is an error, you will see a message like:
```
Test email could not be sent. Mailer Error: <error details>
```

---

## Debugging Issues

If the email fails to send, here are some common troubleshooting steps:

1. **Check SMTP Credentials**:
   - Ensure the values in your [`.env`](.env ) file are correct.
   - Double-check the SMTP host, username, password, and port.

2. **Enable SMTP Debugging**:
   - To get detailed error messages, enable SMTP debugging by modifying the following line in [`test_email.php`](test_email.php ):
     ```php
     $mail->SMTPDebug = SMTP::DEBUG_SERVER; // Enable verbose debug output
     ```

3. **Firewall or Network Restrictions**:
   - Ensure your network or server allows outbound connections to the SMTP server's port (e.g., `465` or `587`).

4. **Gmail-Specific Issues**:
   - If using Gmail, enable "Less Secure App Access" or use an **App Password**.

---

## File Structure

```
composer-mailer/
├── vendor/                 # Composer dependencies
├── .env                    # Environment variables (not included in version control)
├── composer.json           # Composer configuration
├── composer.lock           # Composer lock file
├── test_email.php          # Main script to send emails
```

---

## Example Output

### Success:
```
Test email has been sent successfully.
```

### Failure:
```
Test email could not be sent. Mailer Error: SMTP Error: Could not authenticate.
```

---

## Additional Notes

- **Security**: Never commit your [`.env`](.env ) file to version control. Always keep sensitive information secure.
- **PHPMailer Documentation**: For more advanced usage, refer to the [PHPMailer documentation](https://github.com/PHPMailer/PHPMailer).
- **SMTP Provider Settings**: Check your email provider's documentation for the correct SMTP settings.

---

## License

This project is open-source and available under the MIT License.

---

Feel free to reach out if you encounter any issues or need further assistance!