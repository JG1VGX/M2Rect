### _M2Rect.pl_
# M/2 Log Rectifier

Assigning appropriate TX#s to QSO records in a Cabrillo format
for Multi 2TX contest log

rin fukuda, jg1vgx@jarl.com

Requirements
------------
You need Perl package to run this script. If you are on Windows, use ActivePerl (http://www.activestates.com/) or Windows Services for Unix (http://www.microsoft.com/japan/windows/sfu/), which also includes Perl. 

How to Use
----------
1. Prepare your Multi/2TX contest log in a Cabrillo format. Column positions, especially for the last TX#, should be strictly observed, otherwise this script won't work. Headers (before the QSO: section) and footers (after the QSO: section, usually END-OF-LOG: only) can contain any length of lines.
Information about Cabrillo format is available here.
http://www.kkn.net/~trey/cabrillo/qso-template.html

2. Start the script, such as:

    ```
    > perl M2Rect.pl
    ```
    
    then, enter the file name of the Cabrillo log. Hour summary of QSY counts will be shown in the screen. If excess QSYs had been detected, you will be warned. In that case, consider submitting your log into Multi/Multi category rather than Multi/2TX.

3. The correctly numbered new Cabrillo log will be created as "new_" plus original file name. The original Cabrillo log is untouched. In addition, two report files are created.

- bandchanges.txt: Consecutive QSOs on the same band is treated as one in the program. Change# is a serial number for such bundled QSOs. TX#s assigned for each bundle of QSOs are shown.
- qsy_report.txt: Flow of QSYs for entire contest is shown using text graphics. You can count and confirm that the QSY counts are in fact less than eight times for each TX.

Version History
---------------
v0.03 (22 Mar 2006)
- compatibility with Cabrillo logs where TX# is not on column 80

v0.02 (14 Mar 2005)
- Configurable max QSY count
- for ARRL-DX(=6 in addition to 8 for CQ-WW)

v0.01 (10 Dec 2004)
- First Release
- for CQ-WW
