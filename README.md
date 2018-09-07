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


###DIFFERENT NUMBER OF QUESTIONS:

You can edit the index.html file to suport any number of questions. Just create a Google form with the intended number of questions and add/remove the respective variables in the Javascript. The submit URL should refect the changes and look like this:

`https://docs.google.com/forms/d/e/[YOURFORMID]/formResponse?entry.[YOURQUESTION1IDHERE]=[YOURQUESTION1ANSWERHERE]&entry.[YOURQUESTION2IDHERE]=[YOURQUESTION2ANSWERHERE]&submit=Submit`

You can test the form [here](http://jAniceto.github.io/google-custom-form/). The spreadsheet containing the responses can be found [here](https://docs.google.com/spreadsheets/d/1gzMhtf8RAC4XVZlSQsmEx6k0MKXuxW3Buv0QFZ9vMw8/edit#gid=765584236).
