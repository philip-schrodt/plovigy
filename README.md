# plovigy
These are a series of programs inspired by the basic functionality of the [prodigy](http://prodi.gy/) system modified to use keyboard entry and the terminal-based `curses` library. They have been used in various phases of the Political Instability Task Force New Generation Event Coder project (2021-2022) and the formats have gradually morphed away from `prodigy` but should be fairly easy to figure out/modify.

Out of historical circumstance, these are primarily located in https://github.com/openeventdata/plovigy but I'm including this as a stub with the main programs

## plovigy-mark
A lightweight program that duplicates the basic functionality of the "mark" function in the [prodigy](http://prodi.gy/) system using the same input and output formats; output is saved to a file which is coder- and time-stamped rather than to a database.


# plovigy-PITF

## plovigy-PITF-DEDI.py

A subset of `plovigy-mark.py` which uses the PITF-DEDI jsonl format—see the file `plovigy-DEDI-input-sample.jsonl` for a sample of the input—and mostly does simple accept/reject classification without
any other options, though it does allow dates to be moved forward and back. This also does quite a bit of autocoding: see the sample files `autocodes-DEDI.txt` and `autocodes-202212-DEDI.txt`. Requires `utilDEDI.py` 

DEDI is an internal PITF data set on protests which is derived from the government version of the ICEWS event data. `plovigy-PITF-DEDI.py` is just one piece of an extended pipeline used in this production but has been *extensively* used for several years and I've got more documentation for the program if that would be helpful.

## plovigy-PITF-annotate.py

Radical simplification of `plovigy-PITF-DEDI.py` to work with the PITF PLOVER/NGEC human annotations. The more complex `actor-annot-lite` replaces this for annotation purposes, but this forms the basis for the later `plovigy-NGEC` programs.
  
## actor-annot-lite.py/documentation
  
A Python program for annotating event files with sentence segmentation, actor, recipient, and location spans. It is designed to use minimal machine resources—in the Macintosh OS-X system—it takes about 6Mb of memory versus the 350Mb required for a single Google Chrome web page—and does not require connection to a server. The program is implemented using the C/Python `ncurses` terminal emulation and uses a small set of keyboard commands rather than a mouse, and is designed to run on a laptop. Like on an airplane.

# November 2022

## plovigy-NGEC-context.py
plovigy for selecting cases either from the Release data (.json suffix) or from the cases selected by assess_context.py(.txt suffix). Writes to the training-case format: see internal commenting for additional details

## plovigy-NGEC-review.py/.documentation.pdf
plovigy for additional annotating of event training cases and documentation for same. 

