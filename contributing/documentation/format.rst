Documentation Format
====================

La documentazione di Symfony2 utilizza `reStructuredText`_ che utilizza come linguaggio di markup `Sphinx` _ per la generazione dell'output (HTML, PDF, ...).

reStructuredText
----------------

reStructuredText "is an easy-to-read, what-you-see-is-what-you-get plaintext
markup syntax and parser system."

Si può approfondire di più sulla sua sintassi leggengo i documenti esistenti di Symfony2 _ o leggendo la guida `reStructuredText Primer`_ disponibile sul sito ufficial di Sphinx.


Se si ha dimestichezza con Markdown, bisogna fare attenzione alle cose simili, ma differenti: 
* Le liste cominciano all'inizio della linea (non hanno bisogno di indentazione)
* I blocchi di codice utilizzano le doppie apici (````come queste````).

Sphinx
------

Sphinx è un sistema di compilazione che aggiunge alcuni piacevoli strumenti  per creare documentazione da documenti reStructuredText. Come tale, essa aggiunge nuove direttive e
interpreta ruoli di testo definiti nello standard reST ` markup`_. 

Syntax Highlighting
~~~~~~~~~~~~~~~~~~~

Tutti i blocchi di codice utilizzano PHP come linguaggio di default. E possibile cambiarlo la direttiva ``code-block``:

.. code-block:: rst

    .. code-block:: yaml

        { foo: bar, bar: { foo: bar, bar: baz } }

Se il vostro codice PHP comincia con ``<?php``, allora si avrà bisogno di utilizzare ``html+php`` come pseudo-linguaggio:

.. code-block:: rst

    .. code-block:: html+php

        <?php echo $this->foobar(); ?>

.. note::
   La lista dei linguaggi supportati è disponibile nel `sito Pygments`_.

Configurazione Blocks
~~~~~~~~~~~~~~~~~~~~

Ogni volta che si mostra una configurazione, per mostrarla in tutti i formati supportati  bisogna utilizzare la direttiva ``Configurazione-block`` (``PHP``, ``YAML``, and ``XML``):

.. code-block:: rst

    .. Configurazione-block::

        .. code-block:: yaml

            # Configurazione in YAML

        .. code-block:: xml

            <!-- Configurazione in XML //-->

        .. code-block:: php

            // Configurazione in PHP

Il precedente snippet reST mostra un blocco come di seguito:

.. Configurazione-block::

    .. code-block:: yaml

        # Configurazione in YAML

    .. code-block:: xml

        <!-- Configurazione in XML //-->

    .. code-block:: php

        // Configurazione in PHP

.. _reStructuredText:        http://docutils.sf.net/rst.html
.. _Sphinx:                  http://sphinx.pocoo.org/
.. _documents:               http://github.com/symfony/symfony-docs
.. _reStructuredText Primer: http://sphinx.pocoo.org/rest.html
.. _markup:                  http://sphinx.pocoo.org/markup/
.. _Pygments website:        http://pygments.org/languages/