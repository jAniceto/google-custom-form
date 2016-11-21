Custom Google Form
==================

Submit to a google spreadsheet using a form of your own design. No redirect to google "Form compleated" page.


###INSTRUCTIONS:

* Build a google form and make sure it is public. View the form, and click on the "Responses" tab. In the form settings choose "Select response destination" and make sure it logs to a new spreadsheet.

* Go to the live form (Preview button) and view the page source.

* Search for the `form` tag and copy the `action` URL, getting rid of everything after `formResponse?`. Paste the URL in the `baseURL` variable.

* Search the source of the page for this `entry.`. There should be one instace of `entry.` for each question in your form (in this example there are 3). Copy the value after `entry.` and paste them in the `q1ID`, `q1ID`, and `q1ID` variables.

* Do the equivalent to the submit button. Search for the submit button by searching for `name="fbzx" value=`. Copy the value number and paste it on the `submitRef` variable.

* Style your page how you like, put in any sort of behavior you want to have happen when someone submits an entry (we're just having the form field say 'Thank You!'), then put these files on a web server somewhere, and you should now be able to submit data to your custom form, and see it appear in your Google Spreadsheet.


###MULTIPLE QUESTIONS:

Some people have asked about incorporating multiple questions, so I've included an `index2.html` file which shows a form with two questions.

Essentially, you just need to make sure your submit URL looks like this:

```
https://docs.google.com/forms/d/[YOURFORMID]/formResponse?entry.[YOURQUESTION1IDHERE]=[YOURQUESTION1ANSWERHERE]&entry.[YOURQUESTION2IDHERE]=[YOURQUESTION2ANSWERHERE]&submit=Submit
```

where you just keep separating each question and answer with an ampersand.

entry.1=answer1&entry.2=answer2&entry3=answer3

etc.

Good luck! I have put my own sample form online [here](http://mikeheavers.com/lab/google/forms/custom-form.html) and you can view the spreadsheet with the form responses [here](https://docs.google.com/spreadsheets/d/1mzPTZC2YbQpN5IK07Fj4sENj6zajNu6TbFcHo7lD45o).
