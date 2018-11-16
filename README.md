# NLTK-Text-Message-Analysis
A foray into Natural Language Processing using the Natural Language Toolkit to analyze my over 80,000 texts I have saved to my iPhone

 1. Acquire message data following this guide: http://osxdaily.com/2010/07/08/read-iphone-sms-backup/
 2. Use an SQLite reader to read the messages (I used the DB Browser found at https://sqlitebrowser.org/)
 3. Write a query under the "Execute Data" tab to extract the data you want to analyze.
    - I started with the texts and date. My sample query looked like:
    ```
    SELECT message.text, message.date, handle.id
    FROM message, handle
    WHERE message.handle_id = handle.ROWID AND handle.id="+11235554678" --Let +11235554678 be the desire phone number of someone to analyze messages if desired. Else, remove everything after handle.ROWID
    ```
 4. Use NLTK to analyze the data
 
 ## TODO:
  - Plot my varying vocabulary over time using my lexical diversity score and the date timestamp of all my outgoing messages
  - See how many messages I've ever sent versus ever received
  - See how many messages I've sent to and received from one particular person
  - See who says the most words or phrases (e.g. "love" or "I love")
