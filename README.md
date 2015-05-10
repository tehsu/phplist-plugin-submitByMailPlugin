phplist-plugin-submitByMailPlugin
=================================

Elements of a plugin to submit messages to Phplist by mail. This is meant to replace the earlier mail2list plugin.

I have renamed my plugin the submitByMail plugin to avoid confusion with Sawey’s mail2list. It’s a completely independent development based on the PEAR classes and the PHP iMap extension.

There is an edit page allowing each individual list to be configured for submission of messages through email. This page allows the administrator to enter an email address for message submission, as well as a password an the domain of the POP server. In addition an option will be given allowing the mail to be entered through a UNIX pipe (if Phplist is running on the same server). Each list is required to have a different address for submission of messages. Messages collected by POP must be use SSL/TLS and must use the standard port 995.

For each list there are radio buttons specifying whether or not submitted messages should be processed immediately or escrowed for confirmation by the purported sender. Escrowing the message requires a subdirectory for the message file and a database table containing information allowing the message to be retrieved after it is confirmed, or deleted if it is not.

For each list there are radio buttons specifying whether the message should be saved for editing or queued immediately.

Messages submitted are rejected if they do not come from a superuser or the list administrator.

The schedule and template for messages queued immediately are the default values.

There will be page available to each list administrator to allow her/him to collect and process messages for their lists. Optionally this function can be carried out through a command line command, allowing the message collection and processing to be scheduled through cron.

Messages submitted via a UNIX pipe than through POP will be escrowed or processed immediately.

Although I had given up this project earlier, I am again working on it, and have thus far have completed the user interface for configuring lists for email message submission.

A Late Update

May 8, 2015
Development of this plugin is continuing. The latest version is based on the imap PHP extension and the PEAR mime decoder instead of the Manuel Lemos' libraries. Code development is very nearly complete at this point, although nothing has yet been added to the Github repository.

Unlike Sawey's mail2list plugin, the submitByMailPlugin allows for attachments to messages. Each list may have a different email address for submission of messages. The disposition of messages is configurable for each list. Confirmation of submission may be required, if wanted. A list can be configured to save submitted messages as a draft, or to queue messages immediately if the message is acceptable with attachments in the form of proper MIME. Other plugins are given access to submitted messages at the time the messages are saved and when messages are queued.

Current target dates

May 15: complete writing the code and begin tesing
June 15: complete local testing
June 30: issue the first release through Github

After June 30: deal with issues reported by early adopters 
