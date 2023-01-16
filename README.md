from http.server import HTTPServer, BaseHTTPRequestHandler
נגדיר משתנים עבור שם משתמש והסיסמה הנכונים #
username = None
password = None
נטען את הקובץ שמכיל את הנתונים הנכונים #
with open("userpass.txt") as f:
נקרא ונפצל את התוכן של הקובץ לתוך רשימה בה כל איבר הוא שורה #
 txt = f.read().split("\n")
נעבור שורה שורה בקובץ #
for line in txt:
נפצל את השורה על פי הסימן שווה #
 line = line.split("=")
אם זאת השורה של שם המשתמש #
 if "username" in line[0]:
נשמור את האיבר השני וננקה רווחים מיותרים על הדרך #
 username = line[1].strip()
אחרת אם זאת השורה של הסיסמה #
 elif "password" in line[0]:
נשמור את האיבר השני וננקה רווחים מיותרים על הדרך #
 password = line[1].strip()
