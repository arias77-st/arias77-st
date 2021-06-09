from email.mime.text import MIMEText
import smtplib
 
# SMTP認証情報
account = "ogasawara.tsu2244@gmail.com"
password = "Ogasawara2244"
 
# 送受信先
to_email = "ogasawara.tsu2244@gmail.com"
from_email = "ogasawara.tsu2244@gmail.com"
 
# MIMEの作成
subject = "テストメール"
message = "テストメール"
msg = MIMEText(message, "html")
msg["Subject"] = subject
msg["To"] = to_email
msg["From"] = from_email
 
# メール送信処理
server = smtplib.SMTP("smtp.gmail.com", 587)
server.starttls()
server.login(account, password)
server.send_message(msg)
server.quit()
