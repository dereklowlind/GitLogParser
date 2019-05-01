GitLogParser
============

Python script to parse 'git log'

## Usage
Script is intented to be used via commandline where you pipe 'git log' output to the script.  For example:

	> git log | gitLogParser.py

## Example
### git log output:
	commit 187f8311bf31a7c8b7588b9c92dc12878feb5987 (HEAD -> feature, origin/feature)
	Author: dereklowlind <dereklowlind@gmail.com>
	Date:   Mon Apr 29 17:00:20 2019 -0500

		modification 5

	commit fb96a5e967e38c18d29c5cbbd649da0a61fa95f0
	Merge: dddf0e2 4c646cd
	Author: dereklowlind <dereklowlind@gmail.com>
	Date:   Mon Apr 29 16:59:07 2019 -0500

		Merge branch 'master' of https://github.com/dereklowlind/hello-world into feature

	commit 4c646cd7c3e7a5f34d82f6216455f3462ebdffb6
	Author: dereklowlind <38629827+dereklowlind@users.noreply.github.com>
	Date:   Sat Apr 27 22:03:09 2019 -0700

		new modification (#3)

	commit dddf0e2787444fda98b5502e92d7b7d80356cc93
	Merge: f39f39e 175c06c
	Author: dereklowlind <dereklowlind@gmail.com>
	Date:   Sat Apr 27 22:01:09 2019 -0700

		merge fixed

	...

### script output:
	Author           Email                 Hash      Merge     Date                 Message
	========================================================================================
	dereklowlind     dereklowlind@gmail.c  187f831              Mon Apr 29 17:00   modification 5
	dereklowlind     dereklowlind@gmail.c  fb96a5e   dddf0e2     Mon Apr 29 16:59   Merge branch 'master' of https://github.com/dereklowlind/hello-world into feature
	dereklowlind     38629827+dereklowlin  4c646cd              Sat Apr 27 22:03   new modification (#3)
	dereklowlind     dereklowlind@gmail.c  dddf0e2   f39f39e     Sat Apr 27 22:01   merge fixed
	dereklowlind     dereklowlind@gmail.c  175c06c              Sat Apr 27 21:59   modification 4
	dereklowlind     dereklowlind@gmail.c  f39f39e   67d2f2d     Sat Apr 27 21:56   Merge branch 'master' into feature
