 * Project:  Errorreporting: A PHP class dealing with php errors and writting them in a specified file
 * File:     Error.class.php
 *
 * Copyright (c) 2020, Dennis Maina
 * All rights reserved.
 *
# Author 
 DENNIS MAINA
# Contact
* maina@dentricedev.com
# Date 
* Wed ,May 13 2020
# Github 
* github.com/mainadennis
# 
### preriquisites
* A logs folder with read/write permision
# 

 * Redistribution and use in source and binary forms, with or without modification,
 * are permitted provided that the following conditions are met:
 *
 *  - Redistributions of source code must retain the above copyright notice,
 *    this list of conditions and the following disclaimer.
 *  - Redistributions in binary form must reproduce the above copyright notice,
 *    this list of conditions and the following disclaimer in the documentation
 *    and/or other materials provided with the distribution.
 *
 * THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
 * AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
 * IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
 * ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE
 * LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
 * CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
 * SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
 * INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
 * CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
 * ARISING IN ANY WAY OUT OF THE USEOF THIS SOFTWARE, EVEN IF ADVISED OF THE
 * POSSIBILITY OF SUCH DAMAGE.

# To use this class include the following lines of code in your desired php script eg the index.php file
# 
 include('classes/Errors.class.php');
 if (ERR_HANDLER_ENABLED) {
   register_shutdown_function('sysFatalErr');
   set_error_handler('sysErrorhandler');
 }
# 
* This class gets all the errors reported by a php script
* it then classifies them as either fatal or non-fatal according to the error codes
* After an error has been classified it is passed to the respective method:: generalErr,fatalErr
* which then passes the error string and the file to write to to a function log()
# 
* function log() calls the write() funtion which writes or appends the errors into the respective file
* function raStr() adds a random string to the file name improving security for someone trying to access the files from the browser
* if you have a .htaccess file in your log folder the raStr() will be unnecessary.
# 
* The error reporting of this class is set to E_ALL which reports all errors except E_STRICT errors
* you can change that in error_reporting() to your desired but changing this will need a change in the main functions

<h2>PHP ERROR CODES</h2>
<ul> 
<li>E_ERROR 1 fatal runtime error that can be recovered, The execution of the script is stopped immediately</li>
<li>E_WARNING 2 a runtime warning,not fatal and most errors fall here, executiion is not stopped</li>
<li>E_PARSE 4 compile time error,generated by the parser</li>
<li>E_NOTICE 8 runtime notice indicating something that could possibly be an error was encountered when running a script normally</li>
<li>E_CORE_ERROR 16 fatal error that occur during php engine initial startup generated by the core.</li>
<li>E_COMPILE_ERROR 64 fatal errror that occurs while the scriot was being compiled generated by the Zend Scripting engine</li>
<li>E_USER_ERROR 256 a fatal user generated error, generated by the php code using the function trigger_error() rather than the php engine</li>
<li>E_USER_WARNING 512 NON FATAL USER GENERATED WAR MESSAGE, generated by the php code using the function trigger_error() rather than the php engine</li>
<li>E_USER_NOTICE 1024 user generated notice message, generated by the php code using the function trigger_error() rather than the php engine</li>
<li>E_STRICT 2048 Not strictly an error but its triggered whenever php encounters code that could lead to problems or forwad incopatibilities</li>
<li>E_RECOVERABLE_ERROR 4096 A catchable fatal error, although fatal it does not leave the php engine in an unstable state, if the error is not caught the application abborts as it   was an E_ERROR</li>
<li>E_ALL 32767 All errors and warnings except of level E_STRICT</li>
<li>TIP: pssing value (-1) to the error_reporting() function will show every possible error when new levels and constants are added in future php versions</li>
</ul>

# 
## Having troubles implementing?
## Found a bug in the program?
 reach to me maina@dentricedev.com 
 i will be happy to assist 
# 
## want something improved or added?
  fork me at github @ github.com/mainadennis
# 
## Regards,
# [DentriceDev Solutions](https://dentricedev.com).
