# UiPath_Project

## Description
When started, the robot should be able to read all emails sent to troacad2@gmail.com with the subject "Product prices", save the files attached to those, and return an email back to the sender containing an excel with information about the products listed in those attachements (prices on different websites, reviews, etc).

## Details
* The robot checks all the mails inside Inbox, removes them and labels them as ReceivedByProject
* Once received, the mails are saved inside the NewMails folder as folders named after the sender of the mail containing the attached files (NewMails\exemplu@gmail.com\listaproduse.pdf)
* The robot finds the required information about the products in each file, and creates an excel file saved inside the NewProductsInfo folder, in folders named after the senders of the mail (like in NewMails)
* After sending emails containing the required information, the emails are moved to the OldMails folder and the product info is moved to the OldProductsInfo folder, both containing folders named after the current date and time (OldMails\15-45 06-01-2023\example@gmail.com\listaproduse.pdf)

## Current state
* The robot can receive and send emails, but does not search information about the products listed in attachements
* After saving files to NewMails it just copies them to NewProductsInfo and then sends them back
* There are currently 5 sequences inside main:
1. GetMails
2. GetProductsInfo (just copies the file from NewMails to NewProductsInfo for now)
3. SendInfo (send emails containing the files in NewProductsInfo)
4. MoveMails (moves the file from NewMails to OldMails)
5. MoveProdutsInfo (moves the file from NewMails to OldProductsInfo)
