.. title:: Use Cognito Forms to populate Word DOCX templates and then convert to PDF using Zapier integration

.. meta::
   :description: An example of how to auto create Word and PDF documents from Cognito Forms entries using Zapier integration


How to create Word and PDF documents from Cognito Forms in Zapier
=================================================================

In this article, you will learn how to automate the generation of documents in your company. For example, applications, orders, invoices, cards and others. We’ll show you how to create a PDF document from a DOCX template on a `Cognito Form <https://www.cognitoforms.com/>`_ entry with the help of `Processes <../../../user-guide/processes/index.html>`_ in Zapier. 

**Processes** are a `Plumsail Documents <https://plumsail.com/documents/>`_ feature with an intuitive interface for creating documents from templates. 

**Cognito Forms** are an online form builder that allows you to create powerful forms for your website.

We'll connect them in `Zapier <https://zapier.com/apps/plumsail-documents/integrations>`_ to automatically collect data from a Cognito Form, apply it to our template, and generate a new PDF document.

.. contents::
    :local:
    :depth: 2

Create a Form
-------------

We have already created a Cognito Form. We will use data from its submission. If you haven't created Cognito Forms before, follow `this link <https://www.cognitoforms.com/support/15/building-forms/creating-forms>`_ to learn how to do it.

Below is a screenshot of our form:

.. image:: ../../../_static/img/flow/how-tos/Cognito-Form.png
    :alt: Cognito Form

Configure the Process
---------------------

Before creating the Flow, we need to set a Process, which will generate PDF documents from a DOCX template.
 
Create a new process
~~~~~~~~~~~~~~~~~~~~

Go to `the Processes section <https://account.plumsail.com/documents/processes>`_ in your Plumsail account.

Click on the *Add process* button.

.. image:: ../../../_static/img/user-guide/processes/how-tos/add-process-button.png
    :alt: add process button

Set the Process name. Select **DOCX** for a template type.

.. image:: ../../../_static/img/user-guide/processes/how-tos/create-docx-process-forms.png
    :alt: generate PDF from Cognito Forms 

Configure a template
~~~~~~~~~~~~~~~~~~~~

Once you're done with the first step *Create Process*, press the *Next* button, and you’ll proceed to the next step – *Configure Template*.

It includes two substeps:

- Editor;
- Settings.

In `Editor <../../../user-guide/processes/online-editor.html>`_, you can compose the template from scratch or upload a pre-made one. It's also possible to modify the uploaded template online.

Feel free to `download a DOCX template <../../../_static/files/flow/how-tos/Create-Word-and-PDF-template.docx>`_ that we're using in this example for demonstration purposes:

.. image:: ../../../_static/img/flow/how-tos/docx-template_forms_processes.png
    :alt: Docx template

Then upload it to the process.

.. image:: ../../../_static/img/user-guide/processes/how-tos/upload-template.png
    :alt: upload template file

Tempating syntax
*****************
When creating your own templates, mind the templating language. Plumsail Word DOCX templates use a different approach than most other templating solutions. It uses a minimal amount of syntax to make your work done.

In short, the templating engine thinks that everything between curly :code:`{{ }}` brackets is variables where it will apply your specified data. 
Read `this article <../../../document-generation/docx/how-it-works.html>`_ to get familiar with the templating engine.


Test template
*************

You can test a template as well, to see how it will look at the end. After clicking on the *Test template* button, you’ll need to ‘feed’ a template with your data in JSON format. In our case, it might be:

.. code:: json

    {
      "FieldName1": "Value1",
      "FieldName2": "Value2",
      "FieldName3": "Value3",
      "FieldName4": "Value4"
    }


.. image:: ../../../_static/img/flow/how-tos/test-template-forms-processes.png
    :alt: test template

It’s testing. We’re going to apply the data from the Cognito form to our template. 

Once you've tested the template, press *Save&Next* to proceed further - to the **Settings** substep.

- Switch to an active mode to remove Plumsail watermarks from resulting documents
- Fill in the name of the result file
- Select PDF format for the output file
- `Protect the result PDF <../configure-settings.html#add-watermark>`_ if you wish

.. image:: ../../../_static/img/flow/how-tos/configure-template-forms.png
    :alt: Configure template

Delivery
~~~~~~~~

The next step is delivery. For demonstrating purpose, we’ll store the result file in `OneDrive <../../../user-guide/processes/deliveries/one-drive.html>`_. But there are `other options <../../../user-guide/processes/create-delivery.html#list-of-available-deliveries>`_.

Select the folder where the ready document will be saved. Fill in the file's name. 

.. image:: ../../../_static/img/flow/how-tos/onedrive-forms.png
    :alt: create pdf from template on form submission

You can configure as many deliveries as you need.

Start the Process
~~~~~~~~~~~~~~~~~
We will start our Process from Zapier. 

Create a Zap
------------
Zap is an automated connection between web services in Zapier. 
You can create it from scratch following the steps explained below.


Or you can utilize the zap template. Click **Use this zap**, and then just customize the steps as it's described further in this article.

|Widget|

.. |Widget| raw:: html

    <script type="text/javascript" src="https://zapier.com/apps/embed/widget.js?guided_zaps=134340"></script>

This is how our Zap looks:

.. image:: ../../../_static/img/flow/how-tos/zap-excel-cognito.png
    :alt: xlsx to pdf from Cognito Forms Zap

Below is a step-by-step description.

New entry in Cognito Forms
~~~~~~~~~~~~~~~~~~~~~~~~~~

We need to start the Zap everytime somebody submits our stationery request form. For that, search for  *Cognito Forms* in Zapier and add *New entry* as a trigger.

If this is your first Zap with Cognito Forms, on this step, sign in to your Cognito Account from Zapier to use your forms inside Zaps.

Then, you'll need to pick the form you want to track in the dropdown.

.. image:: ../../../_static/img/flow/how-tos/customize-docx-cognito.png
    :alt: Cognito Form trigger

The last thing to do with the trigger - **Find data**. Press "Test trigger" to find data. It will allow you to use the trigger output on the next step.

.. image:: ../../../_static/img/flow/how-tos/test-cognito-zap-trigger.png
    :alt: Test Cognito Forms trigger to find data

Start process in Plumsail Documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once the trigger is set, search for Plumsail Documents and add an action *Start process*.

.. image:: ../../../_static/img/user-guide/processes/how-tos/start-process-zapier.png
    :alt: start process from Zapier action

Click Continue. If this is your first Zap, at this point, you'll need to Sign in to your Plumsail Account from Zapier to establish a connection between the app and your account. If you already have a Plumsail account tied to the app, you can add another one at this step, and use it instead.

Customize Start Process
***********************

Choose the process you want to start by this Zap from the dropdown. 

Then, you need to specify data by completing the fields. They have the same names as tokens in the template. This data will be applied to the template to personalize documents every time a Cognito form is entered.

Use the output from the trigger to specify values:

.. image:: ../../../_static/img/flow/how-tos/json-docx-zap-cognito.png
    :alt: specify data

Our Zap is ready. See how the resulting file looks:

.. image:: ../../../_static/img/flow/how-tos/Plumsail-Forms-DOCX-PDF-Template-PDF.png
    :alt: pdf from Cognito form result file


Sign up for Plumsail Documents
------------------------------

As you can see, it's simple to automize the generation of documents on Cognito Forms submission. If you're new to Plumsail Documents, `register an account <https://auth.plumsail.com/Account/Register?ReturnUrl=https://account.plumsail.com/documents/processes/reg>`_ to get a free 30-day trial.

.. hint:: See how to `create PDF documents from an XLSX template from Cognito Forms entries in Zapier <../../../user-guide/processes/examples/create-Excel-and-pdf-documents-from-cognito-forms-zapier.html>`_.