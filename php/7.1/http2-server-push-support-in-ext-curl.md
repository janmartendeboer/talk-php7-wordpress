# HTTP/2 server push support in ext/curl

Support for server push has been added to the CURL extension (requires version 7.46 and above). This can be leveraged through the curl_multi_setopt() function with the new CURLMOPT_PUSHFUNCTION constant. The constants CURL_PUSH_OK and CURL_PUSH_DENY have also been added so that the execution of the server push callback can either be approved or denied.
