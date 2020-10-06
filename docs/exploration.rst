Data exploration
================

Fundamentals / Basics
---------------------

We skip past all of the options on the front page looking for ``data``, and happily there's a section called `How to use ATUS microdata files <https://www.bls.gov/tus/howto.htm>`_. Let's look there.

On that page, there's a link to a PDF called `American Time Use Survey User’s Guide <https://www.bls.gov/tus/atususersguide.pdf>`_. 

Now I'm reading that document.

----

Here's a fun little nugget:

    Many other countries have done or currently conduct time-use surveys. Time-use data have been collected on all continents except Antarctica.

Well, that seems fun. A rabbit hole for a different time.

----

There's a fascinating section in here about the history / motivation around the ATUS. The original goal of the ATUS was to measure the amount of *unpaid work*, and even though the survey began in 2003, the federal government first took the concept seriously in 1991.

----

Our first table! The "estimated annual sample size by ATUS sampling strata, 2003." Not gonna lie, there is a whole lot of information about survey design that is basically greek to me. 

---- 

Whoa!

    The ATUS was designed so that organizations can sponsor a module, or series of questions on a special topic usually related to time use, at the end of the survey.

Here are the three modules in there:

1. *Eating and Health*. 2006-08, 2014-16 ("examine relationships between time use; purchasing, preparing, and consuming food; and obesity.")
2. *Well-Being*. 2010, 2012, 2013 ("how people felt during three randomly selected activities")
3. *Leave*. 2011, 2017-18. ("use and access to paid and unpaid leave and the flexibility of their work schedules").  

----

Here's the structure of the code:

    Coders at the telephone center assign a 6-digit classification code to each diary activity. The first two digits represent the major activity category; the next two digits represent the second-tier level of detail; and the final two digits represent the third, most detailed level of activity.

Thinking ahead a bit, this feels ripe for using `d3-hierarchy <https://github.com/d3/d3-hierarchy>`_. I'm imagining a dynamic `treemap <https://github.com/d3/d3-hierarchy#treemap>`_. 

----

In section 6, there's a list of all of the data file types. It's not obvious to me whether we have access to these files. If we do, holy smokes, that's neat. Looks like the magic key for linking these files is ``TUCASEID``. 

----

Interestingly, looks like there are a few traditional metrics used:

- Average hours per day
- Daily participation rate
- Number of participants
- Average hours per day of participants

It sure does seem like we'd be well to write some sort of library / API to the data to make this sort of computation / querying easier. Another rabbit hole.

----

There's more. But this is it for now.