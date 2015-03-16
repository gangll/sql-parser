 = sql-parser =

 sql-parser is parser copy-and-paste from <flex & biosn>

 - generates Reverse Polish Notation (RPN) of SQL statements
 - integrates with GO's yacc and nex instead of YACC/BISON

I wrote this code to get acquainted with GO and SQL for further develop purpose. This is a subset of SQL. The ultimate definitions for SQL are the standards documents published by ANSI and
ISO including ISO/IEC 9075-2:2003, which defines SQL, and a variety of related documents
that define the way to embed SQL in other programming languages and in XML.

== Installation ==

  $export GOPATH=/tmp/go
  $go get github.com/soforth/sql-parser

Run:

  $make
  $./sql-parser

== Example ==

  $cat sql
  insert into `t1` select * from t2 where t2.c > 100;
  $./sql-parser < sql
  SELECTALL
  TABLE t2
  FIELDNAME t2.c
  NUMBER 100
  CMP 2
  WHERE
  SELECT 0 1 1
  INSERTSELECT 0 t
  STMT
  
