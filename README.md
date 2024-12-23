java c
CIT   593:   Introduction to Computer Systems
Midterm:   FALL   2017
Part   I – Short Answer Questions {20   points}   (Provide brief   answers to   the   following   questions)
1)       Convert the following decimal #’s   into 8-bit   2’s   complement   binary   numbers      their   HEX   equivalent:
a)       #17                   in   binary:    0001 0001                                                                            in   hex: x11                                                                                                                                    
b)       #-17               in   binary:    1110   1111                                                                            in   hex: xEF                                                                                                                                    
c)       #128          in   binary:    cannot fit   in 8-bits                                 in   hex:   N/A,   but   not x80                                                         
d)       #-128       in   binary:      1000   0000                                                                              in   hex: x80                                                                                                  
2)       The following are 2’s complement   binary   numbers.      Perform. the   following   operations    indicate if any of the operations generate   overflow.
a)         1100 +   11                                                                                                             =   1011                                                                                                                                                            overflow?    NO
b)       100000000 +   110000                                              = 011110000                                                                                                                     overflow?    YES
c)         01111 + 011                                                                                          =   10010                                                                                                                                              overflow?    YES
d)       10001   - xA                                                                                                       =   10111                                                                                                                                                overflow?      NO
3)       The format for a   32-bit   Floating   Point #   is shown   below.      For
S   (1-bit)
Exponent (8-bits)
Fraction   (23-bits)
1
00000111
10100000000000000000000
a)       Is the   number   positive   or   negative? _negative                                                                                                                           
b)       Accounting for the   bias   (127), what   is the actual value of   the   exponent?
7-127   = -120                                                                                                
c)       What   is the fractional   component   in   decimal: _101   =   0.5   +   .125   =   .625                                                               
d)       E.c. (2 points) Convert the entire # to   decimal   form
-1.625 x 2-120                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       
4)       What   is the address space,   addressability,   and total   capacity   of the   LC4s   memory?
Address space   = _216                                                                                                                                                                                                
Addressability = _16-bit                                                                                                                  
Total capacity = _216    x   16-bit = 65,536 drawers   *   16   bits   per   drawer   =   1,048,576   bits   =
131,072   bytes =   131kB total capacity                                                                      


5)       What   is the difference   between combinational   logic and   sequential   logic?
The output of   combinational logic depends only   on   a   combination   of   its   inputs,   while   the   output of   sequential logic depends on a   combination   of   its   inputs   and in some   cases   its   previous output.
6)       What   is the difference   between a   D-latch   and   a   D-flip/flop?
A D-latch’s output   follows   the input,   whenever its   WE is high.    A   DFF’s   only accepts   new   input at the   transition of   the clk   (from   0   to 1   for   a positive   edge   DFF).
7)       Briefly explain the   purpose   of feedback   in   logic   circuits.Feedback connects   the output back to   the input   of   a   logic   circuit,   giving   it   the   ability   to   use   its last output as apossible input!      This   enables   the   device   to behave   as   a sequential   logic         device, and potentially store data   from one input combination   to   the   next.
8)       From the   perspective of the growth   of   an   ISA,   why   doesn’t   the   program   memory   contain   the exact control   signals for   a   CPU?
I代 写CIT 593: Introduction to Computer Systems Midterm: FALL 2017C/C++
代做程序编程语言f   the   program   memory   actually   stored   the   full   set   of   control   signals, if   a   future   version   of   the ISA required more hardware   to implement new   instructions,   more   control signals   would   likely be required, expanding the   width of   program   memory   and breaking   backwards   compatibility   with   the previous processor’s ISA.
9)       If a   CPU   has   a CLK   signal   with   a   frequency   of   20   Hz,   and   it   takes   30   ms   (recall   the   unit   milli   =   10-3) for   its   register file to fetch or store   new   data,   how fast   must the   ALU   be   to   complete computations within   1 cycle of the   clock?
CLK’s period = 1/20Hz   = 50ms
Recall that the output of   the register   file   connects   to   the   input   of   the ALU,   and   the   output   of
the   ALU   back   to   the   register   file.    So   data   must   be   fetched   from   the   register   and   the
calculation required   for   whatever instruction the CPU is   working   on,   must be   completed   in   under 50ms.
Say   for a read-only instruction, data takes 30ms   to   read,   the ALU   must   complete   its   work in   50-30ms, or   just   20ms.


Part   II -   Long   Form. Questions {80   points}:
1)   {20   points}   For   parts   (a)-(g)   below,   refer to the following sequential   logic circuit:

a)   {2   points} Write out the   Boolean   logic function that   describes the above   logic   circuit:   0020
C =    (A   OR   C) AND   (B’)
b)       {1   points}   If an   inverter   has   a   delay of   1ns, an   AND   gate   has   a   delay   of   2ns,   and   an   OR   gate   has a delay of 3ns, what   is   the   propagation   delay   of   the   above   logic   circuit?
Propagation Delay (worst case): OR + AND = 3ns   + 2ns   =   5ns   (OR   and   INVrun   in parallel,   so   we   only have   to consider the longer operation   (OR) and   the AND   gate)
[Best case: INV + AND = 1ns+2ns = 3ns   (if C’s   last output   was   1,   then   there   is   no   delay   with   the   OR gate and its output   (1) is   available   as   the   input   of the AND gate)]
c)       {5   points} Create   atruth table   for   the   above   logic   circuit;   it   should   have   5   rows   and “arrows”   indicating any sequence   necessary to   move from one   row to the   next.

d)       {1   pt}   For each   row   of your truth table, go   back   and   identify   the “actions”   of   the   logic   circuit.
e)       {5   points} Generate a timing   diagram for   this   logic   circuit;   it   should   encompass   all   actions   from your truth table.
(many   possible solutions,   left   as an exercise for the   students)
   f)          {1   pt}   Is this   logic circuit a   latch   or   a   flip/flop?      Why?
A latch because new inputs   aren’t   accepted as   the   transition   of the change   of   the   inputs,   they are accepted anytime   the inputs   are   correct.
   g)       {5   points}   Draw out the CMOS   implementation   for   the   above   logic   circuit
(must show the actual   feedback   wire   to get   full credit – labeling   is   not sufficient)



2)       {20   points} The table   below shows the contents   of   a   region   of   User   Program   Memory   in
PennSim.   First convert the   machine   instructions you see   here to an   equivalent   sequence   of   assembly   instructions so you can   read them.       Write your answers directly in   the   tables   below.    After you   have done this, show what   would   happen   when the   program   is   executed by filling   in the second table which shows the   state   of   all   of   the   registers   at   the   start   of   each   instruction cycle.   For the   register values   R0-R7 you only   need to fill   in the   value   of   the   register that   has changed from the   previous cycle,   if any.   Keep   the   PSR   in   HEX.      For   R0-R7   you   may   use either decimal or   HEX   (but   indicate which   is   which   with   a   leading #   or   x).      Hint:         start   by   looking   at   the   four   bit   opcode   - be   careful   how   you   breakup   the   16   bit   fields,   one   bit can make a   big   difference.

NOTE: this   column   is   state   ofthe   machine   when   your   program   begins.
Refer to this column   when you execute your   first assembly instruction.


3)         {20   points} The   2-bit wide control signal:   RegInputMux.CTL   is one of few   control   signals   that   can   be   determined solely from the value of the OpCode   of any   instruction   in   the   LC4-ISA.      Recall   that   the
Decoder   is   responsible for examining an   instruction’s OpCode and   determining the   control   signals   necessary to setup the datapath for the   instruction.      In the   truth table   below,   all   of the   possible   LC4   OpCode combinations are   listed   by category.
a)         {15   points}   Use the   ISA to determine the value of the   2-bits   of   RegInputMux.CTL for   each   instruction   category   listed and fill   in those   missing values   in the truth table shown   below. For   any   instructions   that   result   in a don’tcare   (X), simply fill   in with   a   0. Some   OpCodes   are   not   used   in   the   LC4, you’ll see those combinations   blacked out.

The outputs that are highlighted yellow,   are   the only   ones   that   will   be   used   in   the   PLA
b)         {5   points}   Using the completed truth table, create a   PLA that   can   be   used   in   the   decoder to   generate   the   2-bits of   RegInputMux.CTL.    Your   PLA should   have 4   inputs and 2   outputs.

   
   

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
