# NLTK-Text-Message-Analysis
A foray into Natural Language Processing using the Natural Language Toolkit to analyze my over 80,000 texts I have saved to my iPhone

 1. Acquire message data following this guide: http://osxdaily.com/2010/07/08/read-iphone-sms-backup/
 2. Use an SQLite reader to read the messages (I used the DB Browser found at https://sqlitebrowser.org/)
 3. Write a query under the "Execute Data" tab to extract the data you want to analyze.
    - I started with the texts and date. My sample query looked like:
    ```
    SELECT message.text, message.date, handle.id
    FROM message, handle
    WHERE message.handle_id = handle.ROWID AND handle.id="+11235554678"
    ```
 4. Use NLTK to analyze the data
