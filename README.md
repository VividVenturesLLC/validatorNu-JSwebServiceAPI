# validatorNu-JSwebServiceAPI
Validate an HTML5 target document  

 Description :
 
           This script will send the contents of the local web
           page under test in POST format as multipart/form-data
           to https://validator.nu following the API requirements.
					 OR
           Send the URL of a hosted web page in the GET format

           For example in the browsers URL field enter one of these:
            https://validator.nu/?doc=http%3A%2F%2Fvividventures.biz
              Expect the results of the validation in web page format
            https://validator.nu/?doc=http%3A%2F%2Fvividventures.biz&out=json
              Expect the results of the validation in json format
              
   Input  : 
   
            The a)contents or b)web-url of the page under test
            The script figures out which it will be depending on
            where the file is served.  a) if local and b) if hosted.

   Output :
   
            As a console.log message something like
            status = 'Ok: No detectable HTML5 errors in data tested at validator.nu'
                   = 'Error: Invalid HTML5 in data tested at validator.nu'
                   = 'Undefined: No testing was performed.'

            As an innerHTML insertion into the document under test

   Usage:
   
           Insert this script into the bottom of your web page, just above
           the body end tag. For example:

             <!--This is where the simple error message will be placed-->
             <p id="validation_log" style="background-color:DarkKhaki "></p>
             <!--Run the html validation test against the markup of current page-->
             <script src="test_valid_html.js"></script>
             </body></html><!--Ref only - obviously do not insert these end tags-->

   Requires :
   
           The following external files, functions need to be available
           
              The webservice at https://validator.nu

             (For some reason jQuery does not seem to do
              multipart/form-data with the validator.nu API
              which means this code is in native XMLHttpRequest
              NO jQuery!)

   Reference:
   
      https://github.com/validator/validator/wiki
      https://wiki.whatwg.org/wiki/Validator.nu_Web_Service_Interface
      http://en.wikipedia.org/wiki/Query_string
      http://en.wikipedia.org/wiki/URI_scheme
      https://developer.mozilla.org/en-US/docs/Web/API/FormData/append
      https://developer.mozilla.org/en-US/docs/Web/Guide/Using_FormData_Objects
      https://developer.mozilla.org/en-US/docs/AJAX/Getting_Started
