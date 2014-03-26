Setting up InterMine projects in Eclipse
==============================================

The InterMine checkout includes configuration to open the various code modules as Eclipse projects. This document explains how to set up your new checkout in Eclipse.

Starting up Eclipse
-------------------------------

Open Eclipse, if it is the first time you have used it click on the arrow icon to bring up the work environment:

To import the InterMine projects:

1. Select 'File' -> 'Import'.
2. From the dialog select 'General' then 'Existing Projects into Workspace' and click Next.
3. Choose `git/intermine` (or whatever the root directory of your InterMine checkout is) as the root directory to import from.
4. A long list of projects will appear, leave them all selected and click Finish.
5. The workspace will take some time to build. If you are running eclipse on a new checkout of InterMine there initially be some errors. This is because some packages depend on code that is auto-generated from model XML files. To fix this you need to run some ant targets at the command line and refresh. You only need to do this the first time you set up Eclipse.
6. Run ant with no arguments in the following directories:

* intermine/objectstore/model/testmodel
* intermine/integrate/model/fulldata
* intermine/api/test
* intermine/pathquery/main
* intermine/api/model/userprofile
* bio/test-all/dbmodel

Or just run as a single command:

.. code-block:: bash

        (cd intermine/objectstore/model/testmodel && ant clean-all && ant) && (cd intermine/integrate/model/fulldata && ant clean && ant) && (cd intermine/pathquery/main && ant clean && ant) && (cd intermine/api/model/userprofile && ant clean && ant) && (cd bio/test-all/dbmodel && ant clean && ant build-db) && (cd intermine/objectstore/test && ant clean && ant) && (cd bio/core/main && ant clean && ant) 

.. note::

    For the final directory you will first need to set up a properties file for the bio tests (see :doc:`instructions running the bio tests </get-started/intermine-tests>`) and may need to run `ant clean build-db` if prompted to do so.


7. Now select all projects in the Project Explorer and Refresh. There should no longer be any errors. 

.. index:: Eclipse, Intellij, IDE
