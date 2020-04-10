# Strings that matches

Write a Scheme program that display the equal part of 2 strings. Display "*" if the characters are different:

ANSWER:

(define match<br/>
&emsp;(lambda (u v)<br/>
&emsp;&emsp;(if (or (string=? u "") (string=? v ""))<br/>
&emsp;&emsp;&emsp;""<br/>
&emsp;&emsp;&emsp;(let ( (uh (string-ref u 0)) (vh (string-ref v 0))<br/>
&emsp;&emsp;&emsp;&emsp;&emsp;  (s (match (substring u 1) (substring v 1)))<br/>
&emsp;&emsp;&emsp;&emsp;&emsp;  )<br/>
&emsp;&emsp;&emsp;&emsp;(if (char=? uh vh)<br/>
&emsp;&emsp;&emsp;&emsp;&emsp; (string-append (make-string 1 uh) s)<br/>
&emsp;&emsp;&emsp;&emsp;&emsp; (string-append "*" s)<br/>
&emsp;&emsp;&emsp;&emsp;&emsp; )<br/>
&emsp;&emsp;&emsp;&emsp;)<br/>
&emsp;&emsp;&emsp;)<br/>
&emsp;&emsp;)<br/>
)<br/>

(match "hel" "miaoo"); ->  "****o"<br/>

(match "superman" "superwoman"); ->  "super***"<br/>