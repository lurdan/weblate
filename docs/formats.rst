.. _formats:

Supported formats
=================

Weblate supports any format understood by Translate-toolkit, however each
format being slightly different, there might be some issues with not well
tested formats.

.. seealso:: `Supported formats in translate-toolkit`_


Weblate does support both monolingual and bilingual formats. Bilingual formats
store two languages in single file - source and translation (typical examples
is :ref:`gettext`, :ref:`xliff` or :ref:`apple`). On the other side,
monolingual formats identify the string by ID and each language file contains
only mapping of those to given language (typically :ref:`aresource`). Some file
formats are used in both variants, see detailed description below.

For correct use of monolingual files, Weblate requires access to file
containing complete list of strings to translate with their source - this file
is called :guilabel:`template` within Weblate, though the naming might vary in
your application.

.. _gettext:

GNU Gettext
-----------

Most widely used format in translating free software. This was first format
supported by Weblate and still has best support.

Weblate supports contextual information stored in the file, adjusting it's
headers or linking to corresponding source files.

.. seealso:: https://en.wikipedia.org/wiki/Gettext

Monolingual Gettext
+++++++++++++++++++

Some projects decide to use Gettext as monolingual formats - they code just IDs
in their source code and the string needs to be translated to all languages,
including English. Weblate does support this, though you have to choose explicitely
this file format when importing resources into Weblate.

.. _xliff:

XLIFF
-----

XML based format created to standardize translation files, but in the end it
is one of many standards in this area.

XLIFF is usually used as bilingual.

.. seealso:: https://en.wikipedia.org/wiki/XLIFF

Java properties
---------------

Native Java format for translations.

Java properties are usually used as bilingual.

.. seealso:: https://en.wikipedia.org/wiki/.properties

Qt Linguist .ts
---------------

Translation format used in Qt based applications.

Qt Linguist files are used as both bilingual and monolingual.

.. seealso:: http://qt-project.org/doc/qt-4.8/linguist-manual.html

.. _aresource:

Android string resources
------------------------

Android specific file format for translating applications.

Android string resources are monolingual, the :guilabel:`template` file being
stored in different location than others :file:`res/values/strings.xml`.

.. seealso:: https://developer.android.com/guide/topics/resources/string-resource.html

.. note::

    This format is not yet supported by Translate-toolkit (merge request is
    pending), but Weblate includes own support for it.

.. _apple:

Apple OS X strings
------------------

Apple specific file format for translating applications, used for both OS X
and iPhone/iPad application translations.

Apple OS X strings are usually used as bilingual.

.. seealso:: https://developer.apple.com/library/mac/#documentation/MacOSX/Conceptual/BPInternational/Articles/StringsFiles.html

.. note::

    Apple OS X strings are half broken in translate-toolkit 1.9.0 (it will
    generate corrupted files while saving), please use Git snapshot for
    handling these.

PHP files
---------

PHP files can be processed directly, though currently Translate-toolkit has
some problems writing them properly, so please double check that your files
won't get corrupted.

Sample file which should work:

.. code-block:: php

    <?php

    $string['foo'] = 'This is foo string';


Others
------

As already mentioned, all Translate-toolkit formats are supported, but they
did not (yet) receive deeper testing.

.. seealso:: `Supported formats in translate-toolkit`_
   
.. _Supported formats in translate-toolkit: http://docs.translatehouse.org/projects/translate-toolkit/en/latest/formats/index.html
