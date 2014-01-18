# Europython 2010 python-csp sprint report

[Europython](http://www.europython.eu/ "Europython website") was
excellent this year and while the range of talks was very wide, the main
themes seemed to be web scripting and web applications, virtual machines
and concurrency. [Russel Winder](http://www.russel.org.uk/) gave a
keynote on the future of multicore computers and their implications, and
a longer talk about Python and the CSP style of concurrency, [Michael
Sparks](http://yeoldeclue.com/cgi-bin/blog/blog.cgi) gave a lightening
talk about his work on
[Kamaelia](http://www.kamaelia.org/Home.html),??[Andrew
Francis](http://andrewfr.wordpress.com/) talked about implementing
ALTing in Stackless Python and [Tony Ibbs](http://tonyibbs.co.uk/)
talked about KBus, which is like DBus but sensible, and I gave an
introductory talk on our
[python-csp](http://code.google.com/p/python-csp/) project. Following
Europython, Russel has written up his own [overview of the
event](http://www.russel.org.uk/blog/2010-07-28-19-15.html) and Guido
van Rossum has [a nice
post](http://mail.python.org/pipermail/python-dev/2010-July/102306.html)
on his experience of the conference, which mentions CSP related work.
[slideshare id=4849500&doc=pythoncsp-100727083606-phpapp02] **python-csp
sprint report** Post-talks we had two days of Sprints and, having never
been to a Sprint before I'm really amazed at how much we managed to get
done in the??[python-csp](http://code.google.com/p/python-csp/)??sprint
over such a short amount of time. I concentrated on the online tutorial
which was well overdue for an overhaul, and the below is just a brief
account of all our other activities -- apologies if I've missed anyone
out or mis-attributed anything:

-   Fabian Kreutz fixed and merged Russel's Python3 port into the
    default repository, closed a bunch of ancient branches, tidied up
    our strategy for importing the code library, fixed a whole load of
    bugs and hosted a Mercurial clone of the main repository on
    BitBucket for us.
-   Russel started a MacOS port, found a whole world of issues with
    that, and fixed a few bugs.
-   Richard Taylor joined us on the Friday and helped configure Linux to
    solve the "too many open files on disk" OS error that is thrown when
    too many channels or processes are created. Tony Heskett told us how
    to fix the same problem on Mac OS. Richard also gave us some really
    great ideas about how to use the POSIX standard to finish off Sam
    Wilson's work on a C implementation of channels.
-   Joe Metcalfe, Wout Tankink, Urban Skudnik and others went through
    the tutorials in some detail, fixing bugs and posting a bunch of bug
    reports. Fabian tried to eliminate some of the dependencies from the
    examples and make them a bit easier to understand. Urban also wrote
    a channel poisoning example and the tutorial page that goes with it.
-   Michael Sparks had to go home, but joined us over IRC and gave us a
    better understanding of the differences between Kamaelia and other
    asynchronous forms of message passing and the CSP style of
    programming. Later Michael produced a really interesting [OCCAM
    model](http://pastebin.com/B1kqx88G) of one form of Kamaelia
    synchronisation primitive, which has been a good prompt to sort out
    guarded ALTing for python-csp.
-   Stefan Schwarzer went through our testing strategy and started
    formalising a really neat way to unit test python-csp code and wrote
    up some unit tests for many of the built-in processes we have in the
    library. Stefan also got us thinking about??licensing issues for
    python-csp, which probably deserves a wider discussion elsewhere.??
-   Andrew Francis dropped in briefly on his way to the PyPy sprint, and
    sent over a deadlock detection algorithm and some other ideas.

Thanks to everyone who came along to the Sprint, it was great fun and
hopefully we can keep up some momentum. During the Sprint we added six
new project members with commit "privileges" and set up a [public
mailing list](http://groups.google.com/group/python-csp). If you were at
the Sprint or already had commit access to the repository you should
already have received an invite to the list, but if not it is public so
feel free to join.


*Sarah Mount*
