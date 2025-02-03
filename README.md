# mailmerge

"Mail merge" is a process that uses an addressbook or mailing list
database to personalize "form letters" where variables in the letter
are substituted with values from the database.  I recall using this
system in DOS-era WordPerfect but I'm sure personalized form letters
predate digital word processing.

This incarnation of mailmerge is a command line tool designed to work
with GMail (although it could easily be adapted to other mail
systems).

# Usage

`mailmerge` takes a single argument - the file containing the template
and data.

The template file should have three sections divided by two lines
containing the seperator token #---#.  These sections contain:

  1. Header variables (from, subject) in YAML format,
  2. The email body in Python string template format, and
  3. Tab seperated values (TSV) to sub into (1) and (2) with labeled columns

Two column names in the TSV file have special meaning.  The 'email' column
will be the recipient.  The 'cc' column, if present, will be CCed.

A working example is provided.
