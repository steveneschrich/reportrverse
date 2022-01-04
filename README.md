# reportrverse
A collection of packages for reporting, particularly from survey-type data, in R.

The goal of this collection is to make reporting on surveys, questionnaires and form-based input relatively easy to accomplish.

NOTE: This is fairly focused on research use cases (see below for the packages) and may not work for a variety of use cases, but they do work for mine.

# Data Import
As noted, there are several types of data that I try to handle in this framework. The overall structure would be to create individual forms using a web-based tool (e.g., REDCap or Moodle) then collect data. The data import components work to load the data from appropriate source program exports and get them into a reasonable form for reporting. Currently, there are the following packages:

- redcapimportr: This is as you would expect, an importer for REDCap data. There is an excellent importer tool that already exists, which queries the API to get real-time exports from the system. This package takes the `R Export` option from REDCap and imports it into data frames for use.
- moodleimportr: An importer for Moodle. There is an option within Moodle (at least ours) to create questionnaires within a class. We use it to ask students to evaluate the lectures provided. The data can be exported from Moodle, then imported using this library.

# Templating
Writing reports involves the use of a pretty docx or pdf templates for the final product. I wrote a base package `dsreportr` as a template library then extended it using several concrete examples (`qsctemplates` and `mcctemplates`). 

- dsreportr: This is a package (stands for data science reporting template) that provides a generic template (with a default image as banner) for reports. Some of the more important pieces of the package include code for reporting on loaded packages, environment, etc and a mechanism for finding the banner based on YAML header from a markdown document. The goal is to provide as minimal as possible additional packages that inherit functionality from this package and only add absolutely necessary bits (like a new banner image).
- qsctemplates: A template package based on dsreportr for use by the PHSU-MCC U54 Partnership. It includes a partnership-wide template, as well as a qsc (Quantitative Sciences Core) template.

# Reporting
This is still evolving, but there are several packages that support reporting either in tabular or graphical form. Can you do this with all of the wonderful tools in R? Absolutely. I just packaged some default routines together to make it quicker/easier to produce nice summarizations of the type of data that I use.

- evrt: This is an evaluation reporting tool. Briefly, it allows for summarization, tables and figures for evaluations that were collected via REDCap or other tool. 
- u54reportr: As part of the PHSU-MCC U54 Partnership, we have developed a package/REDCap forms for data collection and reporting of key grant outcomes (such as papers/grants submitted). 
- 
