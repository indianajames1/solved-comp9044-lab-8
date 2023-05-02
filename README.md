Download Link: https://assignmentchef.com/product/solved-comp9044-lab-8
<br>
Before the lab you should re-read the relevant lecture slides and their accompanying examples.

Create a new directory for this lab called lab08, change to this directory, and fetch the provided code for this week by running these commands:

$ <strong>mkdir lab08</strong>

$ <strong>cd lab08</strong>

$ <strong>2041 fetch lab08</strong>

Or, if you’re not working on CSE, you can download the provided code as a <a href="https://cgi.cse.unsw.edu.au/~cs2041/20T2/lab/08/provided.zip">zip</a> <a href="https://cgi.cse.unsw.edu.au/~cs2041/20T2/lab/08/provided.zip">file</a> or a <a href="https://cgi.cse.unsw.edu.au/~cs2041/20T2/lab/08/provided.tar">tar</a> <a href="https://cgi.cse.unsw.edu.au/~cs2041/20T2/lab/08/provided.tar">file</a>.

Write a Shell script courses.sh which given a course prefix, e.g. COMP, prints all the course code and name for all UNSW shell_courses with that prefix offered this year on the Kensington Campus. For example:

$ <strong>./courses.sh VISN</strong>

VISN1101 Seeing the World: Perspectives from Vision Science VISN1111 Geometrical and Physical Optics

VISN1221 Visual Optics

VISN2111 Ocular Anatomy and Physiology

VISN2211 Organisation and Function of the Visual System

VISN3111 Development and Aging of the Visual System

VISN4016 Vision Science Honours

<strong>./courses.sh COMP|tail</strong>

COMP9511 Human Computer Interaction

COMP9517 Computer Vision

COMP9596 Research Project

COMP9801 Extended Design and Analysis of Algorithms COMP9814 Extended Artificial Intelligence

COMP9844 Extended Neural Networks and Deep Learning

COMP9900 Information Technology Project

COMP9991 Research Project A

COMP9992 Research Project B

COMP9993 Research Project C

Your program must be POSIX compatible Shell. You can assume anything that works with the version of /bin/dash on CSE systems is POSIX compatible.

You are not permitted to use other languages such as Perl, Python, C, …

You are permitted to use programs such as egrep, sed, sort, uniq.

Hints:

The information you need for course code prefix COMP can be found in this web page:

<a href="http://www.timetable.unsw.edu.au/current/COMPKENS.html">http://www.timetable.unsw.edu.au/current/COMPKENS.htm</a><a href="http://www.timetable.unsw.edu.au/current/COMPKENS.html"><sub>l</sub></a><a href="http://www.timetable.unsw.edu.au/current/COMPKENS.html">.</a> You can assume this is the case for all prefixes.

The command curl will download a URL and print it to standard output.

<table width="961">

 <tbody>

  <tr>

   <td width="961">$ <strong>curl –location –silent http://www.timetable.unsw.edu.au/current/COMPKENS.html|head</strong>&lt;title&gt;Class Search by Teaching Period&lt;/title&gt;&lt;link rel=”stylesheet” type=”text/css” href=”../layout/2020/myunsw.css”&gt; &lt;head&gt;&lt;meta http-equiv=”Content-Type” content=”text/html; charset=iso-8859-1″&gt; &lt;table width=”100%” cellspacing=”0″ cellpadding=”0″&gt;&lt;form name=”googleForm” method=”GET” action=”http://www.google.com/u/theuniversityofnewsouthwales” target=”_blank”&gt;&lt;tr&gt;&lt;td width=”30%” style=”height:120px; border-bottom:10px solid #FFCC00; background-color:#fff;”&gt;&lt;a href=”http://www.unsw.edu.au” target=”_blank”&gt;&lt;img border=”0″ src=”/images-timetable/banner2020.jpg” alt=”TheUniversity of New South Wales” width=”836″ height=”179″ style=”float:left; margin-left:20px; margin-top:25px;”&gt;&lt;/a&gt;&lt;/td&gt;&lt;td width=”70%” style=”height:120px; border-bottom:10px solid #FFCC00; background-color:#fff; vertical-align:bottom; ” align=”right”&gt;$</td>

  </tr>

 </tbody>

</table>

In a script it is best run as curl –silent so it doesn’t print extra information on standard error.

The –location is required so curl will follow a HTTP redirect from the URL.

The wget -q -O- could also be used.

You may find uniq’s -w option useful when removing duplicate courses.

When you think your program is working, you can use autotest to run some simple automated tests:

$ <strong>2041 autotest shell_courses</strong>

When you are finished working on this exercise, you must submit your work by running give:

$ <strong>give cs2041 lab08_shell_courses courses.sh</strong>

before Tuesday 28 July 18 00 to obtain the marks for this lab exercise.

Write a Perl script courses.pl which given a course prefix, e.g. COMP, prints all the course code and name for all UNSW courses with that prefix offered this year on the Kensington Campus. For example:

<strong>./courses.pl VISN</strong>

VISN1101 Seeing the World: Perspectives from Vision Science VISN1111 Geometrical and Physical Optics

VISN1221 Visual Optics

VISN2111 Ocular Anatomy and Physiology

VISN2211 Organisation and Function of the Visual System

VISN3111 Development and Aging of the Visual System

VISN4016 Vision Science Honours

<strong>./courses.pl COMP|tail</strong>

COMP9511 Human Computer Interaction

COMP9517 Computer Vision

COMP9596 Research Project

COMP9801 Extended Design and Analysis of Algorithms COMP9814 Extended Artificial Intelligence

COMP9844 Extended Neural Networks and Deep Learning

COMP9900 Information Technology Project

COMP9991 Research Project A

COMP9992 Research Project B

COMP9993 Research Project C

Your answer must be Perl only.

You may not run external programs, e.g. via system or backquotes.

Hints:

The information you need for course code prefix COMP can be found in this web page: <a href="http://www.timetable.unsw.edu.au/current/COMPKENS.html">http://www.timetable.unsw.edu.au/current/COMPKENS.htm</a><a href="http://www.timetable.unsw.edu.au/current/COMPKENS.html"><sub>l</sub></a><a href="http://www.timetable.unsw.edu.au/current/COMPKENS.html">.</a> You can assume this is the case for all prefixes.

The Perl module LWP::Simple provides a very simple way to get a web page, e.g:

You will need to remove duplicate entries for some courses.

When you think your program is working, you can use autotest to run some simple automated tests:

$ <strong>2041 autotest perl_courses</strong>

When you are finished working on this exercise, you must submit your work by running give:

$ <strong>give cs2041 lab08_perl_courses courses.pl</strong>

before Tuesday 28 July 18 00 to obtain the marks for this lab exercise.

Write a Perl script timetable.pl which given course codes prints an ASCII timetable of their lecture times for this year in the format shown in the example below.

<table width="961">

 <tbody>

  <tr>

   <td width="961">$ <strong>./timetable.pl COMP2041 MATH2400 MATH2859</strong>Mon   Tue   Wed   Thu   Fri09:00     L                       L10:00     L                       L11:00           L           L     L12:00           L 13:0014:00           L15:00           L16:0017:0018:0019:0020:00$ <strong>./timetable.pl COMP9044 COMP6771 GSOE9820</strong>Mon   Tue   Wed   Thu   Fri 09:0010:00                             L11:00                             L12:0013:00                 L14:00           L     L15:00           L16:00                       L17:00                       L18:00                       L19:00                       L20:00</td>

  </tr>

 </tbody>

</table>

You can assume that a course’s lecture times will be found in a web page equivalent to: <a href="http://timetable.unsw.edu.au/current/COMP2041.html">http</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">://</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">timetable</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">.</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">unsw</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">.</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">edu</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">.</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">au</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">/</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">current</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">/</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">MATH</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">1131.</a><a href="http://timetable.unsw.edu.au/current/COMP2041.html">html</a>.

Hint: if you find it difficult to use a regex to extract the line containing the lecture description, split the page into line match a previous line, then skip a certain number of lines.

You assume there are no lectures on weekends, and no lectures before 09 00 or after 21 00 Your answer must be Perl only.

You may not run external programs, e.g. via system or backquotes.

If a course is running in multiple terms print all the terms.

If th                     lti l      t                  i t ll th       t              f                 l

If there are multiple streams print all the streams, for example:

$ <strong>./timetable.pl COMP1511</strong>

Mon   Tue   Wed   Thu   Fri

09:00           L

10:00           L

11:00                 L

12:00                 L

13:00

14:00

15:00

16:00                       L

17:00                       L

18:00

19:00

20:00

$ <strong>./timetable.pl MATH1131</strong>

Mon   Tue   Wed   Thu   Fri

09:00           L

10:00           L

11:00

12:00                 L

13:00     L     L     L

14:00     L     L           L     L

15:00     L     L           L     L

16:00     L           L     L 17:00           L

18:00

19:00

20:00

Note the correct output in all the above examples will change when next term’s lectures are added to the timetable.

When you think your program is working, you can use autotest to run some simple automated tests:

$ <strong>2041 autotest timetable</strong>

When you are finished working on this exercise, you must submit your work by running give:

$ <strong>give cs2041 lab08_timetable timetable.pl</strong>

before Tuesday 28 July 18 00 to obtain the marks for this lab exercise.

When you are finished each exercises make sure you submit your work by running give.

You can run give multiple times. Only your last submission will be marked.

Don’t submit any exercises you haven’t attempted.

If you are working at home, you may find it more convenient to upload your work via <a href="https://cgi.cse.unsw.edu.au/~give/Student/give.php">g</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/give.php">ive</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/give.php">‘</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/give.php">s</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/give.php">web</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/give.php">interface</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/give.php">.</a>

Remember you have until Tuesday 28 July 18 00 to submit your work.

You cannot obtain marks by e-mailing your code to tutors or lecturers.

You check the files you have submitted <a href="https://cgi.cse.unsw.edu.au/~cs2041/20T2/student/">here</a>.

Automarking will be run by the lecturer several days after the submission deadline, using test cases different to those autotest runs for you. (Hint: do your own testing as well as running autotest.)

<a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">After</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">automarking</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">is</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">run</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">by</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">the</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">lecturer</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">you</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">can</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">view</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">y</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">our</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">results</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">here</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">.</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">The</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">resulting</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">mark</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">will</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">also</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">be</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">available</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">via</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">g</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">ive</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">‘</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">s</a> <a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">web interface</a><a href="https://cgi.cse.unsw.edu.au/~give/Student/sturec.php">.</a>