## version 10.10.28 (October 28th 2010) ##

  * user can now select the number of threads for the parallel interpreter
  * minor GUI improvements: mnemonics, recall last export image dimension...

## version 10.10.27 (October 27th 2010) ##

  * fixed the non-detection of duplicate classes

## version 10.10.26 (October 26th 2010) ##

  * added a web link to the tutorial
  * added an about box
  * changed the application layout
  * choice between 3 plotting styles (dots, lines, dots+lines); addresses [issue 9](https://code.google.com/p/acumen-language/issues/detail?id=9)

## version 10.10.25 (October 25th 2010) ##

  * the object are plotted in the order they were created

## version 10.10.23 (October 23th 2010) ##

  * added "upload" action to sbt file that uploads a release on google code ([issue 30](https://code.google.com/p/acumen-language/issues/detail?id=30))
  * the version number is now based on date in the sbt file
  * fixed the UI hanging when pressing pause bug ([issue 29](https://code.google.com/p/acumen-language/issues/detail?id=29))

## version 10.10.11 (October 19th 2010) ##

  * added a _back_ button ([issue 6](https://code.google.com/p/acumen-language/issues/detail?id=6))
  * display cursor information on one line (fixes [issue 1](https://code.google.com/p/acumen-language/issues/detail?id=1))
  * fixed the store pretty printing bug ([issue 24](https://code.google.com/p/acumen-language/issues/detail?id=24))
  * allows for hiding magic fields and nextChild fields ([issue 2](https://code.google.com/p/acumen-language/issues/detail?id=2))
  * fixed the "Magic not found" bug in the GUI ([issue 31](https://code.google.com/p/acumen-language/issues/detail?id=31))
  * added an export image option
  * switched to hi constrast icons

## version 10.10.11 (October 11th 2010) ##

  * Changed the build system from ant to sbt; addresses [issue 28](https://code.google.com/p/acumen-language/issues/detail?id=28). The generated archive is now much smaller.
  * The random tests using scalacheck work again.


## version 10.09.30 (September 30th 2010) ##

  * it is now possible to create objects inside Main's private section; fixes [issue 25](https://code.google.com/p/acumen-language/issues/detail?id=25)
  * `~=` is now interpreted; fixes [issue 23](https://code.google.com/p/acumen-language/issues/detail?id=23)
  * it is now possible to move one's direct child to one of its children; fixes [issue 22](https://code.google.com/p/acumen-language/issues/detail?id=22)
  * semicolons are now accepted at the end of an instruction block, but are optional; addresses [issue 20](https://code.google.com/p/acumen-language/issues/detail?id=20)
  * variable and class identifiers are now free to start with either a lowercase or an upprcase letter; they may also contain underscores; addresses [issue 19](https://code.google.com/p/acumen-language/issues/detail?id=19)
  * Exception generation was not localized in Acumen's internal source code. This made it harder to keep manuals and tutorials consistent, and to check user-level error reports for consistency and style. This has been fixed by localizing in one place where the text for user-level error reports is generated; addresses [issue 17](https://code.google.com/p/acumen-language/issues/detail?id=17)
  * it is now allowed to write `if condition statements end` (without an `else` clause); addresses [issue 16](https://code.google.com/p/acumen-language/issues/detail?id=16)
  * no more mode passed to Main: use private variable instead; addresses [issue 12](https://code.google.com/p/acumen-language/issues/detail?id=12)
  * the convention is now that Main's first argument is called `simulator`; addresses [issue 11](https://code.google.com/p/acumen-language/issues/detail?id=11)
  * gensym is now local (as opposed to accessing a global counter): objects ids are now hierarchical (e.g. `#1.0.2`)
  * the application logic of the UI is now clean and separate from the interaction/drawing code
  * switch from `SwingWorker` to actor based concurrency for the UI
  * turned names into atoms (huge speedup)
  * conformance tests of reference and parallel interpreters are run on every example (`ant test`)
  * added a benchmark command-line option for parallel interpreter (`bench`)
  * added a parallel interpreter (command-line only for now)
  * got rid of explicit "init" in the UI
  * merged play and pause buttons
  * several little fixes I don't remember