How to use custom fonts and add multi-lingual support to converting HTML to PDF
##################################################################

.. contents::
    :local:
    :depth: 1

Using custom fonts
-------------------

Plumsail Documents action `Convert HTML to PDF <https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-html-to-pdf>`_
supports several common fonts out of the box. For example, Times New Roman or Arial:

.. code-block::

  <!DOCTYPE html>
  <html>
    <body>
      <p style="font-family:Times New Roman;">Times New Roman</p>
      <pstyle="font-family:Arial;">Arial</p>
    </body>
  </html>

.. image:: ../../../_static/img/flow/how-tos/convert-html2pdf-fonts1.png
    :alt: Fonts

Also It's possible to use CSS inside HTML code to set a default font or apply the font to a specific section of the document:

.. code-block::

  <!DOCTYPE html>
    <html>
    <head>
      <style>
          p.impact {
          font-family: Impact, Charcoal, sans-serif;
      }
      </style>
    </head>
    <body>

        <h1>CSS font-family</h1>
        <p class="impact">Paragraph</p>

    </body>
    </html>


.. image:: ../../../_static/img/flow/how-tos/convert-html2pdf-fonts2.png
    :alt: Fonts

Using external fonts
-------------------

Convert HTML to PDF suppoorts external fonts as well. It's a common case when you need to include external fonts, 

for example, `Google fonts <https://fonts.google.com/>`_. ThE Source HTML might be following:

.. code-block::

  <html style="color:blue;" lang="en">
  <head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap" rel="stylesheet">
  </head>
  <body>
    <p style="font-family:Roboto, cursive;">A custom font from fonts.google.com</p>
  </body>
  </html>

.. image:: ../../../_static/img/flow/how-tos/convert-html2pdf-fonts3.png
    :alt: Fonts


Support of Unicode characters
-----------------------------
Some fonts do not support foreign characters. Thus, to support specific language 
you may need to add some specific font that supports the language.

it is possible to generate PDFs with foreign languages, or languages that contain special characters such as £.
Convert HTML to PDF supports most of what is supported by UTF-8. However you need to add the following line in the HTML head element

.. code-block::

    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">. 


.. image:: ../../../_static/img/flow/how-tos/action-with-charset.png
    :alt: Convert HTML to PDF

Let's take this HTML:

.. code-block::

    <html>
      <head>
      </head>
        <body>
          <p>¿Qué es Unicode</p>
        </body>
    </html>

Without this code charset=UTF-8, the result will look like this:

.. image:: ../../../_static/img/flow/how-tos/result-without-charset.png
    :alt: Fonts

After adding this part unicode characters should be converted properly.

.. code-block::

    <html>
      <head>
      <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
      </head>
        <body>
          <p>¿Qué es Unicode</p>
        </body>
    </html>

.. image:: ../../../_static/img/flow/how-tos/result-with-charset.png
    :alt: Fonts


These are supported languages: Albanian, Arabic,
Armenian, Bulgarian, Traditional and Simplified Chinese, Croatian, Czech, Danish, 
Dutch, Esperanto, Finnish, French, Georgian, German, Greek, 
Hebrey, Hungarian, Icelandic, Igbo, Interlingua, Italian, Japanese, 
Korean, Lithuanian, Macedonian, Maltese, Mongolian, Occitan, Persian,
Polish, Portuguese, Romanian, Russian, Serbian, Slovenian, Spanish, 
Swedish, Thai, Ukrainian, Upper Sorbian, Turkish, Uyghur, Vietnamese, and Welsh.

Conclusion
##################################################################

Plumsail `Convert HTML to PDF <https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#convert-html-to-pdf>`_ is a usefull tool and supports special characters and many languages.

.. Hint:: Please have a look at this article `How to convert HTML to PDF in Power Automate (Microsoft Flow) and Azure Logic Apps <https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/convert-html-to-pdf.html>`_ .