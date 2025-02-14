java c
Midterm   1 Review   Lab
Principles   of Functional   Programming
Spring   2025


1          Preamble
1.1          Midterm   1   Topics
The   topics   you   can   expect   to   be   tested   on   the   first   midterm   are:
•      Types
•      Evaluation
–      Declarations
–    Bindings
–      Function   calls
•    Equivalence   (including totality)
•      Recursion   (including   tail-recursion)
•   Induction
–   Weak/standard
–    Strong
–      Structural
•      Lists
•      Datatypes
•    Trees
•   Work/Span
Here   is   a   collection   of advice   regarding   how   to   prepare   for   the   upcoming   midterm:
1.      List out the topics that   you   require   the   most   review   on   and   complete   review   lab   problems   that   test   those   concepts.
•    Note:   Problems   have   been   labeled   by   the   most   relevant   topics   that   they   test.
2.    Review   your   homeworks   with   a   focus   on   the   mistakes   you   made   or   the   problems   you   missed.   Make   sure   to   understand   why   your   solution   was   incorrect   and   please   ask   a   TA   if you   need   help   understanding   why!
•    Note:    Exam      questions      will   likely   be   easier   than   homework   questions.      However,   a   deeper   conceptual   understanding   will   be   beneficial   regardless.
3.    Make   a   cheat   sheet!    The   professors   will   usually   allow   a   cheat   sheet   on   the   exam.    Some   helpful   things   to   put   on   your   cheat   sheet   are:
•      definitions   (e.g.   totality,   valuability,   extensional   equivalence)
•      interesting   function   implementations      (i.e.       functions   that   you   didn’t   know   how   to   implement   upon   first   glance)
•    common   mistakes   you   made   on   previous   assignments   and   how   to   avoid   them
•    SML   syntax,   in   case   you   are   still   rusty   in   certain   areas
•   words   of   encouragement   :)
4.      Revisit   past   labs   and   lecture   notes   for   further   practice/review.
2          Conceptual   T/F
For   each   of the   following   tasks,   indicate   whether   the   statement   is   true   or   false.
2.1            Basics   Task   2.1.
Expressions   that   are   not   well-typed   will   not   be   evaluated.
Task   2.2.
If an   expression   is   well-typed,   then   it   is   valuable.
Task   2.3.
If   e1   =→   e2,   then   e1      e2   .
Task   2.4.
If   e1      e1   =→   e2   .
Task   2.5.
SML   evaluates   the   arguments   to   a   function   before   stepping   through   the   body   of the   function.
Task   2.6.
If a function   f       :       t1       ->      t2   is valuable, then   it   is   total.
Task   2.7.
case         (3      +         1)         of         (2      +         2)      =>       "   four   "       |         _       =>         "   not         four   "   reduces   to      "   four   "   .
Task   2.8.
fn         (x         :         int)         :         int    =>      x      +       1    +       1 reduces to   fn       (x       :         int)       :         int    =>      x      +      2
.
Task   2.9.
The   following   declares   a   recursive   function   foo       :       int       -   >       int   :
val         foo       =         (   fn         (0         :         int)    =>      0         |         n      =>       1      +         foo         (n         -         1))


2.2            Induction/Recursion
Task   2.10.
Consider   the   following   declaration   for   foo       :       int       -   >       int.    If we   want   to   prove   a   theorem   about   foo      n   for   all   positive   n       :       int,   we   can   use   simple/weak   induction   to   do   so.
|       foo         (n         :         int)         :         int         =         foo         (n         -         1)    +         foo       (n         -      2)
Task   2.11.
For   which   values   of   (A)   and   (B)   is   f         150   valuable?
|         f         (n         :         int)         :         int         =    f         (n         -         1)      +      f         (n         -      2)
(a)      (A)   is   0   ,    (B)   is   1   .   (b)      (A)   is   0   ,      (B)   is   2   .
(c)      (A)   is   1   ,    (B)   is   2   .
(d)      (A)   is   1   ,      (B)   is   50   .
Task   2.12.
Any   statement   that   can   be   proven   by   weak   induction   can   also   be   proven   by   strong   induction.
For   Tasks   2.13   and   2.14,   suppose   we   are   given   the   implent ions   of   two   functions   f         :       int ->      t   and   g         :       int         ->      t.    We   want   to   show   that      f      x   =   g      x   for   all   values   x   ≥   0      (where x       :       int).    (If a task is false, provide a   (small) correction to the IH that   could potentially   make it   work.)
Task   2.13.
The   following   could   be   a   valid   inductive   hypothesis   in   an   induction   proof:
IH:   Assume that   for   all values   x         :       int,   we   have      .
Task   2.14.In   a   strong   induction   proof,   our   inductive   hypothesis   does   not   have   to   cover   the   values   of   any of   our   base   cases.      For   example,   the   quantification   for   y   in   the   inductive   hypothesis   below   is correct.BC   1:   x   =   0   .      (proof   omitted)   BC   2:   x   =   1   .      (proof   omitted)   IS:   x   >   1   .
IH: Assum代 写Principles of Functional Programming Spring 2025 Midterm 1 Review LabMatlab
代做程序编程语言e   that   for   all   values   y         :       int   satisfying   2   ≤ y   <   x,   we   have      .




Task   2.15.
Implement   the   tail-recursive   helper   function   max   ’ such   that   max   satisfies   the   following   specs:
max : int list -> int option
REQUIRES: true
ENSURES: max L =⇒(SOMENONEv ififvLis the max element ofis empty.L
fun    max ’         (L         :    int         list   ,         acc       :    int         option)       :    int         option         =   raise    Fail         "   your         implementation         here   "
fun    max       (L         :         int         list)         :         int         option         =    max ’       (L,    NONE)
2.3            Lists/Datatypes
Task   2.16.
1::2::3::[]   is a value.
Task   2.17.
The   type   and   datatype   keywords   are   interchangeable   (i.e.   type   and   datatype   declara-
tions   are   the   same).
Task   2.18.
Node   has type   tree, where the   datatype   declaration   for   tree   is   as   follows:   datatype         tree    =         Empty       |       Node       of    tree         *         int         *      tree
Task   2.19.
Given   the   following   datatype   declaration   for   varTree   ,   Two       (One      x,      _   )   is   a   valid   pat-
tern.
datatype         varTree         =         Zero       |       One       of         varTree       |       Two       of         varTree         *
varTree
Task   2.20.
With   structural   induction   on   trees,   we   induct   directly   on   the   number   of nodes   in   the   tree.
2.4            Work/Span
Task   2.21.


The following implementation of rev       :       int       list         -   >         int         list   has O(n) work, where n   is   the   length   of the   input   list.
fun         rev         ([]         :         int    list)         :    int    list         =         []   |         rev         (x::xs)    =         (rev         xs)      @       [x]
Task   2.22.
The   best-case   work   for   calling   inord   is   when   the   input   tree   is   balanced.
fun         inord         (Empty         :    tree)         :         int         list    =         []
|       inord         (Node         (L,    x,      R))      =       (inord    L)      @       (x         ::         (inord    R))
Task   2.23.
When   calculating   span, we   assume   that   expressions   in   tuples   are   evaluated   in   parallel.
Task   2.24.
When   calculating   span,   we   assume   that      val   declarations   in      let ...   in ...   end    expressions
are   executed   in   parallel.
Task   2.25.
Suppose   the   recursive   function   foo   has   input   type   tree.      In   the   tree   method,   the   work   tree
for   foo   always   has   2i    nodes   at   level   i   when   the   input   tree   is   balanced.
Task   2.26.
If the work   of a   function   is   in   O(f(n)), then   its   span   is   also   in   O(f(n)).
3          Types   and   Evaluation
Assume   the   following   is   in   scope:
datatype         tree    =         Empty       |       Node       of    tree         *         int         *      tree
For   each   of   the   following   declarations:
•   If it   typechecks,   give   the   type   of   v;   otherwise   state   “not   well   typed.”    and   explain   why   it   has   no   type.
•   If   v   is   valuable,   give   its   value.      Otherwise,   give      “no   value.”      and   explain   why   it   has   no
value.
Task   3.1.    (Recommended)   val      v      =      3      /      2
Task   3.2.
val      v      =      3      +         2 .   0
Task   3.3.    (Recommended)
val      v      =         1         div         0
Task   3.4.    (Recommended)
val      v      =      fn      x         :         int         =>      x      +         1
Task   3.5.
val      v      =      fn         (x,      y)      =>      x         andalso         y      =      3
Task   3.6.    (Recommended)
val    v      =      fn       (x       :         int)      =>      Node       (Empty ,      x,         Empty)
Task   3.7.
val      v      =         ()
Task   3.8.    (Recommended)
val      v      =         [[1]]         @         []
Task   3.9.
val      v      =         [150]         ::         []
Task   3.10.
val    v      =      fn         (x         :         int)    =>      x         ::       [1]
Task   3.11.    (Recommended)
val    v    =         (   fn         (x         :         int         list)    =>    x         ::         [])         [1]
Task   3.12.
fun      v         (x         :         int)         :         int         =      x      =      3
Task   3.13.    (Recommended)
val      v    =         if         5         >      0      then       "   polly   "         else         150
Task   3.14.
fun      v         (Empty)      =         []
|       v       (Node         (l,      x,      r))      =      v      l      @      x      @      v      r
Task   3.15.    (Recommended)
fun    v         (a,         [])         =         ([a],      a      +         1)
|       v         (   _ ,      x         ::         xs)      =    v       (   not      x,      xs)
Task   3.16.    (Recommended)
val      v      =   let
fun      g         []      =      g         ([   "   150   "   ])
|         g       (x       ::         xs)      =      x         ^      g      xs
in
(g,    g         [],      g         [   "   3   "   ])
end
   
   
   



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
