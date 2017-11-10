Bug reproduce for https://code.djangoproject.com/ticket/28773

The file with syntax error is messagesbug/edu/locale/id_ID/LC_MESSAGES/django.po .
You can look at the file and you can see the syntax error at line 69 .

Using my system (Windows 10, gettext 0.19.8.1) this bug is 100% reproducible using this project:

1. `pip install -r requirements.txt`
2. Delete the django.po file
3. Regenerate the django.po file:

       python manage.py makemessages -l id_ID -v3

   Generated file will contain syntax error again.
