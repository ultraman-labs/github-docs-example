# Best Practices For Writing Documentaion Well

## Step 1 - Using Codeblocks

Codelblocks in markdonw make it _very easy_ for tech people to **copy, paste, share code**.
A good cloud engineer uses codebloacke whenever possible because it allows others to
copy and paste their code to replicate or research issues.


In order to create codeblocks: 
- You need to use three back ticks at the begining of the codeblock, and again at the end of the codeblock. (```)
- Not to be confused with single quotations. (')

```
from flask import Flask, request
import smtplib
from email.mime.text import MIMEText

app = Flask(__name__)

@app.route('/send_email', methods=['POST'])
def send_email():
    if request.method == 'POST':
        try:
            # Extract data from the request
            recipient_email = request.form['recipient_email']
            subject = request.form['subject']
            message = request.form['message']

            # Your email configuration
            sender_email = 'your_email@gmail.com'
            sender_password = 'your_password'

            # Create and send the email
            msg = MIMEText(message)
            msg['From'] = sender_email
            msg['To'] = recipient_email
            msg['Subject'] = subject

            server = smtplib.SMTP('smtp.gmail.com', 587)
            server.starttls()
            server.login(sender_email, sender_password)
            server.sendmail(sender_email, recipient_email, msg.as_string())
            server.quit()

            return "Email sent successfully!"
        except Exception as e:
            return f"Error sending email: {str(e)}"

if __name__ == '__main__':
    app.run(debug=True)
```

When you can, apply syntax highlighting to your codeblocks

```python
from flask import Flask, request
import smtplib
from email.mime.text import MIMEText

app = Flask(__name__)

@app.route('/send_email', methods=['POST'])
def send_email():
    if request.method == 'POST':
        try:
            # Extract data from the request
            recipient_email = request.form['recipient_email']
            subject = request.form['subject']
            message = request.form['message']

            # Your email configuration
            sender_email = 'your_email@gmail.com'
            sender_password = 'your_password'

            # Create and send the email
            msg = MIMEText(message)
            msg['From'] = sender_email
            msg['To'] = recipient_email
            msg['Subject'] = subject

            server = smtplib.SMTP('smtp.gmail.com', 587)
            server.starttls()
            server.login(sender_email, sender_password)
            server.sendmail(sender_email, recipient_email, msg.as_string())
            server.quit()

            return "Email sent successfully!"
        except Exception as e:
            return f"Error sending email: {str(e)}"

if __name__ == '__main__':
    app.run(debug=True)
```

- Take note of where the backtick button is located.
- Generally it appears above the tab key, but this varies depending your keyboard layout.
  
![backtick](https://github.com/ultraman-labs/github-docs-example/assets/59581412/fe57d702-4f7e-43cd-a768-b1437e93a9cb)


#### Good Cloud Engineers ues codeblocks for both code and errors that appear in the console. 


```bash
irb(main):001:0> 1 / 0
ZeroDivisionError: divided by 0
irb(main):002:0>
```
> The abbove snippet is an example codeblock error that appears in Bash.

## Step 3 - Use Github Flavored Markdown Tasks List
Github extends Markdown to hqve a list where you can check off items. <sup>[1]</sup>

- [x] Finish Step 1
- [] Finish Step 2
- [x] Finish Step 3

## Step 4 - Use Emojis (Optional)

Github Flavored Markdown (GFM) supports emoji shortcodes.
Here are some examples:

|Name | Shortcode | Emoji |
| --- | --- | --- |
| Cloud | `:cloud:` | :cloud: |
| Flying Saucer | `:flying_saucer:` | :flying_saucer: |
| Alien | `:alien:` | :alien: |

## Step 5 - How to create a table 

You can use the following format to create tables: 

```md

|Name | Shortcode | Emoji |
| --- | --- | --- |
| Cloud | `:cloud:` | :cloud: |
| Flying Saucer | `:flying_saucer:` | :flying_saucer: |
| Alien | `:alien:` | :alien: |
```

Github extends the funcionalitiy of Markdown tables to provide more alignment and table cell formatting options.[<sup>[2]</sup>](#sources)
## Sources (External References)
- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/) 
- [Basic Writing and Formatting Syntax (Github Flavoured Markdown)](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#quoting-text)
- [GFM - Task Lists](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#task-lists) <sup>[1]</sup>
- [GFM Emoji CheatSheet](https://github.com/ikatyang/emoji-cheat-sheet/)
- [GFM - Tables (with extensions)](https://github.github.com/gfm/#tables-extension-)<sup>[2]</sup>


