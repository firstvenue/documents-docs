Create fillable PDF With Nitro Pro
==================================

You can use `Nitro Pro <https://www.gonitro.com/nps/pro/create-pdf-creator>`_ to create your PDF file with a form. 

First, we need to create a new PDF file:

.. image:: ../../_static/img/document-generation/fill-in-pdf-form-nitro-new.png
    :alt: Nitro Pro new

Then we need to add text which will indicate a field name (click on Type Text in Home section):

.. image:: ../../_static/img/document-generation/fill-in-pdf-form-nitro-add-text.png
    :alt: Nitro Pro add text

After that, we should add a field to our PDF file (Forms section):

.. image:: ../../_static/img/document-generation/fill-in-pdf-form-nitro-add-field.png
    :alt: Nitro Pro add field

Finally, we should specify this field's name. Later you will want to automatically populate values to this form. That is why it is important to assign the correct field name. When populating the form you will submit some object with values. The field name has to match property names in this object. 

For example, you have a field with the name "Text1". In this case, you will need to submit an object with the structure like this to fill this field:

.. code::

    {
      "Text1": "Some value"
    }

Click on the field -> Properties section to change field name:

.. image:: ../../_static/img/document-generation/fill-in-pdf-form-nitro-specify-name.png
    :alt: Nitro Pro specify name

`Download the example of a fillable PDF <../../_static/files/document-generation/demos/fill-in-pdf-form-template.pdf>`_ for this article.

.. image:: ../../_static/img/document-generation/fill-in-pdf-form-template.png
    :alt: Fillable PDF example

And here is the example of the data object that could be used for populating this form:

.. code:: json

  {
    "FirstName": "David",
    "LastName": "Navarro",
    "Address": "3 Main St.",
    "City": "New York",
    "PostalCode": "972013",
    "PhoneNumber": "202-555-0131",
    "Email": "david@sample.com",
    "Activities": "Sports: football, basketball, volleyball",
    "CurrentlyWorking": "No",
    "HistoryCompany": "Acme Corp",
    "HistoryEmploymentSector": "Public",
    "HistorySupervisor": "Derek Clark",
    "HistoryPhoneNumber": "555-777-9999",
    "HistoryPosition": "Marketing director",
    "HistoryDuties": "Developing marketing strategy",
    "HistoryLeaving": "Moving to another city",
    "HistoryContact": "Yes",
    "HistoryEmploymentForm": "Trainee",
    "Date": "06/30/2019", 
    "PersonalDataConsent" : false
  }