
.. i18n: All the Elements of a Complete Workflow
.. i18n: =======================================
..

All the Elements of a Complete Workflow
=======================================

.. i18n: The supplier or purchase order is the document that lets you manage price negotiations, control supplier invoices, handle goods receipts and synchronize all of these documents.
..

The supplier or purchase order is the document that lets you manage price negotiations, control supplier invoices, handle goods receipts and synchronize all of these documents.

.. i18n: Let us start by looking at the following order workflow:
..

Let us start by looking at the following order workflow:

.. i18n: #. Price request to the supplier,
.. i18n: 
.. i18n: #. Confirmation of purchase,
.. i18n: 
.. i18n: #. Receipt and control of products,
.. i18n: 
.. i18n: #. Control of invoicing.
..

#. Price request to the supplier,

#. Confirmation of purchase,

#. Receipt and control of products,

#. Control of invoicing.

.. i18n: Setting up your Database
.. i18n: ------------------------
..

Setting up your Database
------------------------

.. i18n: To set up a system for these examples, create a new database with demonstration data in it, and
.. i18n: select the :guilabel:`Extended` interface when you log in as the *admin* user. You can enter your own
.. i18n: company details when asked, or just use the default if you want.
..

To set up a system for these examples, create a new database with demonstration data in it, and
select the :guilabel:`Extended` interface when you log in as the *admin* user. You can enter your own
company details when asked, or just use the default if you want.

.. i18n: .. index::
.. i18n:    single: module; purchase
..

.. index::
   single: module; purchase

.. i18n: Then, using the Configuration Wizard, select :guilabel:`Purchase Management` in the :guilabel:`Install Applications` section to install the :mod:`purchase` module, which also installs several other modules as dependencies. Continue
.. i18n: the remainder of this chapter logged in as the *admin* user.
..

Then, using the Configuration Wizard, select :guilabel:`Purchase Management` in the :guilabel:`Install Applications` section to install the :mod:`purchase` module, which also installs several other modules as dependencies. Continue
the remainder of this chapter logged in as the *admin* user.

.. i18n: Price Request from the Supplier
.. i18n: -------------------------------
..

Price Request from the Supplier
-------------------------------

.. i18n: To enter data for a new supplier price request (i.e. request for quotation), use the menu :menuselection:`Purchases --> Purchase Management -->
.. i18n: Request for Quotation`. When you click :guilabel:`New`, OpenERP opens a blank request for quotation form that you use for requesting prices from a supplier. This is shown in the figure :ref:`fig-pfrm`. If the price request came from an automatic procurement created by OpenERP, you will find a reference to the document that generated the request in the :guilabel:`Origin` field.
..

To enter data for a new supplier price request (i.e. request for quotation), use the menu :menuselection:`Purchases --> Purchase Management -->
Request for Quotation`. When you click :guilabel:`New`, OpenERP opens a blank request for quotation form that you use for requesting prices from a supplier. This is shown in the figure :ref:`fig-pfrm`. If the price request came from an automatic procurement created by OpenERP, you will find a reference to the document that generated the request in the :guilabel:`Origin` field.

.. i18n: .. _fig-pfrm:
.. i18n: 
.. i18n: .. figure:: images/purchase_form.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Data Entry for a Purchase Order*
..

.. _fig-pfrm:

.. figure:: images/purchase_form.png
   :scale: 75
   :align: center

   *Data Entry for a Purchase Order*

.. i18n: .. index::
.. i18n:    single: module; warning
..

.. index::
   single: module; warning

.. i18n: .. note:: Managing Alerts
.. i18n: 
.. i18n:         If you install the :mod:`warning` module, you will be able to define alerts that appear when the purchaser enters a price request or order. You can set alerts on the product and on the supplier.
..

.. note:: Managing Alerts

        If you install the :mod:`warning` module, you will be able to define alerts that appear when the purchaser enters a price request or order. You can set alerts on the product and on the supplier.

.. i18n: The internal reference, the date and the warehouse the products should be delivered to, are completed automatically by OpenERP, but you can change these values if needed. Next, when you select a supplier, OpenERP automatically completes the contact address for the supplier. The pricelist is also automatically completed from the pricelist in the supplier form. This should bring in all of the conditions that you have negotiated with the supplier for a given period.
..

The internal reference, the date and the warehouse the products should be delivered to, are completed automatically by OpenERP, but you can change these values if needed. Next, when you select a supplier, OpenERP automatically completes the contact address for the supplier. The pricelist is also automatically completed from the pricelist in the supplier form. This should bring in all of the conditions that you have negotiated with the supplier for a given period.

.. i18n: .. tip:: Supplier Selection
.. i18n: 
.. i18n:         Searching for a supplier is limited to all of the partners in the system that have the :guilabel:`Supplier` checkbox checked. If you do not find your supplier, it might be worth checking the whole list of all partners to make sure that the supplier does not yet exist without the Supplier checkbox being checked.
..

.. tip:: Supplier Selection

        Searching for a supplier is limited to all of the partners in the system that have the :guilabel:`Supplier` checkbox checked. If you do not find your supplier, it might be worth checking the whole list of all partners to make sure that the supplier does not yet exist without the Supplier checkbox being checked.

.. i18n: Once the main body of the purchase order has been completed, you can enter the product lines.
..

Once the main body of the purchase order has been completed, you can enter the product lines.

.. i18n: .. figure:: images/purchase_line_form.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Purchase Order Line*
..

.. figure:: images/purchase_line_form.png
   :scale: 75
   :align: center

   *Purchase Order Line*

.. i18n: When you have selected the product, OpenERP automatically completes the other fields in the form:
..

When you have selected the product, OpenERP automatically completes the other fields in the form:

.. i18n: * :guilabel:`Product UoM`, taken from the :guilabel:`Purchase Unit of Measure` field in the product form,
.. i18n: 
.. i18n: * The :guilabel:`Description` of the product in the supplier's language,
.. i18n: 
.. i18n: * :guilabel:`Scheduled Date`, calculated from the order date and the delivery lead time for the supplier (for the given product),
.. i18n: 
.. i18n: * :guilabel:`Unit Price`, taken from the supplier's pricelist,
.. i18n: 
.. i18n: * :guilabel:`Taxes`, taken from the information on the product form and partner form,
.. i18n:   depending on the rules seen in :ref:`Financial Analysis <ch-financial>`.
..

* :guilabel:`Product UoM`, taken from the :guilabel:`Purchase Unit of Measure` field in the product form,

* The :guilabel:`Description` of the product in the supplier's language,

* :guilabel:`Scheduled Date`, calculated from the order date and the delivery lead time for the supplier (for the given product),

* :guilabel:`Unit Price`, taken from the supplier's pricelist,

* :guilabel:`Taxes`, taken from the information on the product form and partner form,
  depending on the rules seen in :ref:`Financial Analysis <ch-financial>`.

.. i18n: .. tip:: Product Wording and Code
.. i18n: 
.. i18n:         When you enter supplier names in the product form, you can set a name and a product code for each individual supplier. If you do that, OpenERP will then use those details instead of your own internal product names for that selected supplier.
..

.. tip:: Product Wording and Code

        When you enter supplier names in the product form, you can set a name and a product code for each individual supplier. If you do that, OpenERP will then use those details instead of your own internal product names for that selected supplier.

.. i18n: If you work with management by case, you can also set the analytic account that should be used to
.. i18n: report all the purchase costs. The costs will then be reported at the receipt of the supplier
.. i18n: invoice.
..

If you work with management by case, you can also set the analytic account that should be used to
report all the purchase costs. The costs will then be reported at the receipt of the supplier
invoice.

.. i18n: .. index::
.. i18n:    single: module; purchase_analytic_analysis
..

.. index::
   single: module; purchase_analytic_analysis

.. i18n: .. tip:: Management by Case
.. i18n: 
.. i18n:    Analytic accounts can be very useful for all companies that manage costs by case, by site, by
.. i18n:    project or by folder.
.. i18n:    To work with several analytic axes, you should install the module :mod:`purchase_analytic_plans`,
.. i18n:    by selecting :guilabel:`Purchase Analytic Plans` in the :guilabel:`Reconfigure` wizard and clicking
.. i18n:    :guilabel:`Configure`.
..

.. tip:: Management by Case

   Analytic accounts can be very useful for all companies that manage costs by case, by site, by
   project or by folder.
   To work with several analytic axes, you should install the module :mod:`purchase_analytic_plans`,
   by selecting :guilabel:`Purchase Analytic Plans` in the :guilabel:`Reconfigure` wizard and clicking
   :guilabel:`Configure`.

.. i18n: .. index::
.. i18n:    single: module; account_analytic_default
.. i18n:    single: module; purchase_analytic_plans
..

.. index::
   single: module; account_analytic_default
   single: module; purchase_analytic_plans

.. i18n: To make sure that the analytic account is automatically selected according to the partner, the date, the
.. i18n: products or the user, you can install the module :mod:`account_analytic_default` (which is installed
.. i18n: automatically as a dependency of :mod:`purchase_analytic_plans`).
..

To make sure that the analytic account is automatically selected according to the partner, the date, the
products or the user, you can install the module :mod:`account_analytic_default` (which is installed
automatically as a dependency of :mod:`purchase_analytic_plans`).

.. i18n: In the :guilabel:`Notes` tab of the product line, you can enter a note that will be attached when the order
.. i18n: confirmation or price quotation is printed. This note can be predefined on the product form to
.. i18n: automatically appear on each order for that product. For example, you can enter “Do not forget to send
.. i18n: by express delivery as specified in our contract reference 1234.”
..

In the :guilabel:`Notes` tab of the product line, you can enter a note that will be attached when the order
confirmation or price quotation is printed. This note can be predefined on the product form to
automatically appear on each order for that product. For example, you can enter “Do not forget to send
by express delivery as specified in our contract reference 1234.”

.. i18n: Once the document has been completed, you can print it as a price estimate to send to
.. i18n: the supplier. You can set a note for the attention of the supplier in the form's third tab.
..

Once the document has been completed, you can print it as a price estimate to send to
the supplier. You can set a note for the attention of the supplier in the form's third tab.

.. i18n: .. figure:: images/purchase_quotation.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Printing the Supplier Price Quotation*
..

.. figure:: images/purchase_quotation.png
   :scale: 75
   :align: center

   *Printing the Supplier Price Quotation*

.. i18n: Then leave the document in the ``Request for Quotation`` state. When you receive a response from the supplier, use the menu
.. i18n: :menuselection:`Purchases --> Purchase Management --> Requests for Quotation`. Select the
.. i18n: order and complete its details.
..

Then leave the document in the ``Request for Quotation`` state. When you receive a response from the supplier, use the menu
:menuselection:`Purchases --> Purchase Management --> Requests for Quotation`. Select the
order and complete its details.

.. i18n: When you want to approve the order, use the button :guilabel:`Convert to Purchase Order`. The price
.. i18n: request then passes into the ``Approved`` state. 
.. i18n: No further changes are possible.
..

When you want to approve the order, use the button :guilabel:`Convert to Purchase Order`. The price
request then passes into the ``Approved`` state. 
No further changes are possible.

.. i18n: .. figure:: images/purchase_process.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Purchase Order Process*
..

.. figure:: images/purchase_process.png
   :scale: 75
   :align: center

   *Purchase Order Process*

.. i18n: Goods Receipt
.. i18n: -------------
..

Goods Receipt
-------------

.. i18n: Once the order has been approved, OpenERP automatically prepares the goods receipt order in the
.. i18n: draft state for you. To get a list of the products you are waiting for from your suppliers, use the
.. i18n: menu :menuselection:`Warehouse --> Warehouse Management --> Incoming Shipments`.
..

Once the order has been approved, OpenERP automatically prepares the goods receipt order in the
draft state for you. To get a list of the products you are waiting for from your suppliers, use the
menu :menuselection:`Warehouse --> Warehouse Management --> Incoming Shipments`.

.. i18n: .. tip:: Purchasing Services
.. i18n: 
.. i18n:     If you buy services from your supplier, OpenERP does not generate a goods receipt note.
.. i18n:     There is no service receipt equivalent to a goods receipt.
..

.. tip:: Purchasing Services

    If you buy services from your supplier, OpenERP does not generate a goods receipt note.
    There is no service receipt equivalent to a goods receipt.

.. i18n: Select the document that corresponds to the item that you are receiving. Usually, the goods receipt
.. i18n: note is found by making a search on the order reference or the supplier name. You can then confirm
.. i18n: the receipt of the products.
..

Select the document that corresponds to the item that you are receiving. Usually, the goods receipt
note is found by making a search on the order reference or the supplier name. You can then confirm
the receipt of the products.

.. i18n: As described in :ref:`ch-stocks`, if you receive only part of the order, OpenERP
.. i18n: manages the remainder of that order.
.. i18n: A second receipt note is then automatically created for the goods not received.
.. i18n: You can cancel it if you think that you will never receive the remaining products.
..

As described in :ref:`ch-stocks`, if you receive only part of the order, OpenERP
manages the remainder of that order.
A second receipt note is then automatically created for the goods not received.
You can cancel it if you think that you will never receive the remaining products.

.. i18n: After receiving the goods, OpenERP will show you which orders are open and the state of their
.. i18n: receipt and invoicing if you return to the list of orders.
..

After receiving the goods, OpenERP will show you which orders are open and the state of their
receipt and invoicing if you return to the list of orders.

.. i18n: .. figure:: images/purchase_list.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *List of Open Orders, and their Receipt and Invoice Status*
..

.. figure:: images/purchase_list.png
   :scale: 75
   :align: center

   *List of Open Orders, and their Receipt and Invoice Status*

.. i18n: Control of Invoicing
.. i18n: --------------------
..

Control of Invoicing
--------------------

.. i18n: To control supplier invoicing, OpenERP provides three systems as standard, which can differ order
.. i18n: by order:
..

To control supplier invoicing, OpenERP provides three systems as standard, which can differ order
by order:

.. i18n: * :guilabel:`From Order` : invoicing based on quantities ordered,
.. i18n: 
.. i18n: * :guilabel:`From Picking` : invoicing based on quantities received,
.. i18n: 
.. i18n: * :guilabel:`Manual` : manual invoicing.
..

* :guilabel:`From Order` : invoicing based on quantities ordered,

* :guilabel:`From Picking` : invoicing based on quantities received,

* :guilabel:`Manual` : manual invoicing.

.. i18n: The mode of invoicing control is set in the second tab of the purchase order in the field
.. i18n: :guilabel:`Invoicing Control`.
..

The mode of invoicing control is set in the second tab of the purchase order in the field
:guilabel:`Invoicing Control`.

.. i18n: .. figure:: images/purchase_form_tab2.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Purchase Order, Invoice Control*
..

.. figure:: images/purchase_form_tab2.png
   :scale: 75
   :align: center

   *Purchase Order, Invoice Control*

.. i18n: .. tip:: Default Value
.. i18n: 
.. i18n:    A company generally uses a single invoicing control method for all of its invoices.
.. i18n:    So you are advised to set a default value in the :guilabel:`Invoicing Control` field after
.. i18n:    installation.
..

.. tip:: Default Value

   A company generally uses a single invoicing control method for all of its invoices.
   So you are advised to set a default value in the :guilabel:`Invoicing Control` field after
   installation.

.. i18n: Control based on Orders
.. i18n: -----------------------
..

Control based on Orders
-----------------------

.. i18n: If you selected your invoicing control based on orders, OpenERP will automatically generate a
.. i18n: supplier invoice in the draft state when the order is confirmed. You can obtain a list of invoices
.. i18n: waiting using the menu :menuselection:`Accounting --> Suppliers --> Supplier Invoices` and enabling
.. i18n: the ``Draft`` filter.
..

If you selected your invoicing control based on orders, OpenERP will automatically generate a
supplier invoice in the draft state when the order is confirmed. You can obtain a list of invoices
waiting using the menu :menuselection:`Accounting --> Suppliers --> Supplier Invoices` and enabling
the ``Draft`` filter.

.. i18n: When you receive a paper invoice from your supplier, all you need to do is validate the invoice pre-
.. i18n: generated by the system. Do not forget to check the price and the quantities. When the invoice is
.. i18n: confirmed, the accounting entries represent the cost of purchase and are automatically entered into
.. i18n: the system.
..

When you receive a paper invoice from your supplier, all you need to do is validate the invoice pre-
generated by the system. Do not forget to check the price and the quantities. When the invoice is
confirmed, the accounting entries represent the cost of purchase and are automatically entered into
the system.

.. i18n: The supplier order is automatically set as ``Paid`` when you pay the supplier invoice.
..

The supplier order is automatically set as ``Paid`` when you pay the supplier invoice.

.. i18n: This method of controlling invoices is often used in service companies, because the invoiced amounts
.. i18n: correspond to the ordered amounts. In logistics, by contrast, you most often work with invoicing
.. i18n: controlled by goods receipt.
..

This method of controlling invoices is often used in service companies, because the invoiced amounts
correspond to the ordered amounts. In logistics, by contrast, you most often work with invoicing
controlled by goods receipt.

.. i18n: Control based on Goods Receipt
.. i18n: ------------------------------
..

Control based on Goods Receipt
------------------------------

.. i18n: To control your supplier invoices based on goods receipt, set the field :guilabel:`Invoicing
.. i18n: Control` on the second tab of the order to :guilabel:`From Picking`.
..

To control your supplier invoices based on goods receipt, set the field :guilabel:`Invoicing
Control` on the second tab of the order to :guilabel:`From Picking`.

.. i18n: In this case, no invoice, draft state or any other, is generated by the order. On the goods receipt
.. i18n: note, the field :guilabel:`Invoice Control` is set to :guilabel:`To Be Invoiced`.
..

In this case, no invoice, draft state or any other, is generated by the order. On the goods receipt
note, the field :guilabel:`Invoice Control` is set to :guilabel:`To Be Invoiced`.

.. i18n: The storesperson can then receive different orders. If he wants to generate the draft invoice for a
.. i18n: goods receipt, he can click the action :guilabel:`Create Invoice`. OpenERP then asks you for the
.. i18n: journal for this invoice. It then opens that or the generated invoices (in the case of creating
.. i18n: invoices for several receipts at one time) which enables you to modify it before confirming it.
..

The storesperson can then receive different orders. If he wants to generate the draft invoice for a
goods receipt, he can click the action :guilabel:`Create Invoice`. OpenERP then asks you for the
journal for this invoice. It then opens that or the generated invoices (in the case of creating
invoices for several receipts at one time) which enables you to modify it before confirming it.

.. i18n: This approach is useful when you receive the invoice at the same time as the item from the supplier.
.. i18n: Usually, invoices are sent by post some days later. In this case, the storesperson leaves the item
.. i18n: unchanged without generating an invoice. Then, once per day or once per week the accountant will
.. i18n: create the draft invoices based on all the receipts for the day. To do that, he uses the menu
.. i18n: :menuselection:`Purchases --> Invoice Control --> Purchase Lines Not Invoiced`. 
.. i18n: He clicks the action :guilabel:`Create invoices` to generate all draft invoices from
.. i18n: the list of receipts that have not yet been invoiced.
..

This approach is useful when you receive the invoice at the same time as the item from the supplier.
Usually, invoices are sent by post some days later. In this case, the storesperson leaves the item
unchanged without generating an invoice. Then, once per day or once per week the accountant will
create the draft invoices based on all the receipts for the day. To do that, he uses the menu
:menuselection:`Purchases --> Invoice Control --> Purchase Lines Not Invoiced`. 
He clicks the action :guilabel:`Create invoices` to generate all draft invoices from
the list of receipts that have not yet been invoiced.

.. i18n: .. index::
.. i18n:    single: accountant
..

.. index::
   single: accountant

.. i18n: At that point, the accountant can decide if he wants to generate an invoice per item or group all items
.. i18n: for the same partner into the same invoice.
..

At that point, the accountant can decide if he wants to generate an invoice per item or group all items
for the same partner into the same invoice.

.. i18n: Invoices are then handled just like those controlled from ``On Order``. Once the invoice arrives at
.. i18n: the accounting service, he just compares it with the invoices waiting to control what the supplier
.. i18n: invoices you.
..

Invoices are then handled just like those controlled from ``On Order``. Once the invoice arrives at
the accounting service, he just compares it with the invoices waiting to control what the supplier
invoices you.

.. i18n: .. index::
.. i18n:    single: module; delivery
..

.. index::
   single: module; delivery

.. i18n: .. tip:: Delivery Charges
.. i18n: 
.. i18n:    To manage delivery charges, install the module :mod:`delivery` using the :guilabel:`Reconfigure` wizard
.. i18n:    and selecting :guilabel:`Delivery Costs` in :guilabel:`Sales Application Configuration` section.
.. i18n:    This will automatically add delivery charges to the creation of the draft invoice as a function
.. i18n:    of the products delivered or ordered.
..

.. tip:: Delivery Charges

   To manage delivery charges, install the module :mod:`delivery` using the :guilabel:`Reconfigure` wizard
   and selecting :guilabel:`Delivery Costs` in :guilabel:`Sales Application Configuration` section.
   This will automatically add delivery charges to the creation of the draft invoice as a function
   of the products delivered or ordered.

.. i18n: .. index:: 
.. i18n:    single: tender
.. i18n:    single: purchase; tender
..

.. index:: 
   single: tender
   single: purchase; tender

.. i18n: Tenders
.. i18n: -------
..

Tenders
-------

.. i18n: .. index::
.. i18n:    single: module; purchase_tender
..

.. index::
   single: module; purchase_tender

.. i18n: To manage tenders, you should use the module :mod:`purchase_requisition`, installed via the
.. i18n: :guilabel:`Purchase Requisition` option in the :guilabel:`Reconfigure` wizard.
.. i18n: This lets you create several
.. i18n: supplier price requests for a single supply requirement. Once the module is installed, OpenERP adds
.. i18n: a new :menuselection:`Purchase Requisitions` menu in :menuselection:`Purchases --> Purchase Management`. You can then define the new tenders.
..

To manage tenders, you should use the module :mod:`purchase_requisition`, installed via the
:guilabel:`Purchase Requisition` option in the :guilabel:`Reconfigure` wizard.
This lets you create several
supplier price requests for a single supply requirement. Once the module is installed, OpenERP adds
a new :menuselection:`Purchase Requisitions` menu in :menuselection:`Purchases --> Purchase Management`. You can then define the new tenders.

.. i18n: .. figure:: images/purchase_tender.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Defining a Tender*
..

.. figure:: images/purchase_tender.png
   :scale: 75
   :align: center

   *Defining a Tender*

.. i18n: To enter data for a new tender, use the menu :menuselection:`Purchases --> Purchase Management -->
.. i18n: Purchase Requisitions` and select :guilabel:`New`. OpenERP then opens a new blank tender form. The reference number
.. i18n: is set by default and you can enter information about your tender in the other fields.
..

To enter data for a new tender, use the menu :menuselection:`Purchases --> Purchase Management -->
Purchase Requisitions` and select :guilabel:`New`. OpenERP then opens a new blank tender form. The reference number
is set by default and you can enter information about your tender in the other fields.

.. i18n: If you want to enter a supplier's response to your tender request, add a new
.. i18n: draft purchase order into the list on the :guilabel:`Quotation` tab of your tender document. 
.. i18n: If you want to revise a supplier price in response to negotiations, edit any 
.. i18n: appropriate purchase order that you have left in the draft state and link that to the tender. 
..

If you want to enter a supplier's response to your tender request, add a new
draft purchase order into the list on the :guilabel:`Quotation` tab of your tender document. 
If you want to revise a supplier price in response to negotiations, edit any 
appropriate purchase order that you have left in the draft state and link that to the tender. 

.. i18n: When one of the orders about a tender is confirmed, all of the other orders are automatically
.. i18n: cancelled by OpenERP if you selected the Purchase Requisition (exclusive) type. That enables you to accept just one order for a particular tender. If you select Multiple requisitions, you can approve several purchase orders without cancelling other orders from this tender.
..

When one of the orders about a tender is confirmed, all of the other orders are automatically
cancelled by OpenERP if you selected the Purchase Requisition (exclusive) type. That enables you to accept just one order for a particular tender. If you select Multiple requisitions, you can approve several purchase orders without cancelling other orders from this tender.

.. i18n: Price Revisions
.. i18n: ---------------
..

Price Revisions
---------------

.. i18n: OpenERP supports several methods of calculating and automatically updating product costs:
..

OpenERP supports several methods of calculating and automatically updating product costs:

.. i18n: * Standard Price: manually fixed, and
.. i18n: 
.. i18n: * Standard Price: revalued automatically and periodically,
.. i18n: 
.. i18n: * Average Price: updated at each receipt to the warehouse.
..

* Standard Price: manually fixed, and

* Standard Price: revalued automatically and periodically,

* Average Price: updated at each receipt to the warehouse.

.. i18n: This cost is used to value your stock and represents your product costs. Included in that cost is
.. i18n: everything directly related to the received cost. You could include such elements as:
..

This cost is used to value your stock and represents your product costs. Included in that cost is
everything directly related to the received cost. You could include such elements as:

.. i18n: * supplier price,
.. i18n: 
.. i18n: * delivery charges,
.. i18n: 
.. i18n: * manufacturing costs,
.. i18n: 
.. i18n: * storage charges.
..

* supplier price,

* delivery charges,

* manufacturing costs,

* storage charges.

.. i18n: Standard Price
.. i18n: ^^^^^^^^^^^^^^
..

Standard Price
^^^^^^^^^^^^^^

.. i18n: The mode of price management for the product is shown in the tab :guilabel:`Information` on the product form.
.. i18n: On each individual product, you can select if you want to work in ``Standard Price`` or on weighted ``Average Price``.
..

The mode of price management for the product is shown in the tab :guilabel:`Information` on the product form.
On each individual product, you can select if you want to work in ``Standard Price`` or on weighted ``Average Price``.

.. i18n: .. tip:: Simplified Interface
.. i18n: 
.. i18n:    If you work in the ``Simplified`` interface mode you will not see the field that lets you
.. i18n:    manage the price calculation mode for a product. In that case, the default value is ``Standard Price``.
..

.. tip:: Simplified Interface

   If you work in the ``Simplified`` interface mode you will not see the field that lets you
   manage the price calculation mode for a product. In that case, the default value is ``Standard Price``.

.. i18n: The ``Standard Price`` setting means that the product cost is fixed manually for each product in the field
.. i18n: :guilabel:`Cost Price`. This is usually revalued once a year based on the average of purchase costs
.. i18n: or manufacturing costs.
..

The ``Standard Price`` setting means that the product cost is fixed manually for each product in the field
:guilabel:`Cost Price`. This is usually revalued once a year based on the average of purchase costs
or manufacturing costs.

.. i18n: You usually use standard costs to manage products where the price hardly changes over the course of
.. i18n: the year. For example, the standard cost could be used to manage books, or the cost of bread.
..

You usually use standard costs to manage products where the price hardly changes over the course of
the year. For example, the standard cost could be used to manage books, or the cost of bread.

.. i18n: Those costs that can be fixed for the whole year bring certain advantages:
..

Those costs that can be fixed for the whole year bring certain advantages:

.. i18n: * you can base the sale price on the product cost and then work with margins rather than 
.. i18n:   a fixed price per product,
.. i18n: 
.. i18n: * accounting is simplified because there is a direct relationship between the value of stock and the
.. i18n:   number of items received.
..

* you can base the sale price on the product cost and then work with margins rather than 
  a fixed price per product,

* accounting is simplified because there is a direct relationship between the value of stock and the
  number of items received.

.. i18n: .. index::
.. i18n:    single: module; product_extended
..

.. index::
   single: module; product_extended

.. i18n: To get an automated periodic revaluation of the standard price you can use the action :guilabel:`Update`
.. i18n: on the product form, enabling you to update prices of all the selected products. 
.. i18n: OpenERP then recalculates the price of the products as a function of the cost of raw materials and the
.. i18n: manufacturing operations given in the routing.
..

To get an automated periodic revaluation of the standard price you can use the action :guilabel:`Update`
on the product form, enabling you to update prices of all the selected products. 
OpenERP then recalculates the price of the products as a function of the cost of raw materials and the
manufacturing operations given in the routing.

.. i18n: Average Price
.. i18n: ^^^^^^^^^^^^^
..

Average Price
^^^^^^^^^^^^^

.. i18n: Working with standard prices does not lend itself well to the management of the cost price of products
.. i18n: when the prices change a lot with the state of the market. This is the case for many commodities and
.. i18n: energy.
..

Working with standard prices does not lend itself well to the management of the cost price of products
when the prices change a lot with the state of the market. This is the case for many commodities and
energy.

.. i18n: In this case, you would want OpenERP to automatically set the price in response to each goods receipt movement
.. i18n: into the warehouse. The deliveries (exit from stock) have no impact on the product price.
..

In this case, you would want OpenERP to automatically set the price in response to each goods receipt movement
into the warehouse. The deliveries (exit from stock) have no impact on the product price.

.. i18n: .. tip:: Calculating the Price
.. i18n: 
.. i18n:    At each goods receipt, the product price is recalculated using the following accounting formula:
.. i18n:    NP = (OP * QS + PP * QR) / (QS + QR), where the following notation is used:
.. i18n: 
.. i18n:    * NP: New Price,
.. i18n: 
.. i18n:    * OP: Old Price,
.. i18n: 
.. i18n:    * QS: Quantity actually in Stock,
.. i18n: 
.. i18n:    * PP: Price Paid for the quantity received,
.. i18n: 
.. i18n:    * QR: Quantity Received.
..

.. tip:: Calculating the Price

   At each goods receipt, the product price is recalculated using the following accounting formula:
   NP = (OP * QS + PP * QR) / (QS + QR), where the following notation is used:

   * NP: New Price,

   * OP: Old Price,

   * QS: Quantity actually in Stock,

   * PP: Price Paid for the quantity received,

   * QR: Quantity Received.

.. i18n: If the products are managed as a weighted average, OpenERP will open a
.. i18n: window that lets you specify the price of the product received at each goods receipt. 
.. i18n: The purchase price is, by default,
.. i18n: set from the purchase order, but you can change the price to add the cost of
.. i18n: delivery to the various received products, for example.
..

If the products are managed as a weighted average, OpenERP will open a
window that lets you specify the price of the product received at each goods receipt. 
The purchase price is, by default,
set from the purchase order, but you can change the price to add the cost of
delivery to the various received products, for example.

.. i18n: .. figure:: images/purchase_pmp.png
.. i18n:    :scale: 75
.. i18n:    :align: center
.. i18n: 
.. i18n:    *Goods Receipt of Products managed in Weighted Average*
..

.. figure:: images/purchase_pmp.png
   :scale: 75
   :align: center

   *Goods Receipt of Products managed in Weighted Average*

.. i18n: Once the receipt has been confirmed, the price is automatically recalculated and entered on the
.. i18n: product form.
..

Once the receipt has been confirmed, the price is automatically recalculated and entered on the
product form.

.. i18n: .. Copyright © Open Object Press. All rights reserved.
..

.. Copyright © Open Object Press. All rights reserved.

.. i18n: .. You may take electronic copy of this publication and distribute it if you don't
.. i18n: .. change the content. You can also print a copy to be read by yourself only.
..

.. You may take electronic copy of this publication and distribute it if you don't
.. change the content. You can also print a copy to be read by yourself only.

.. i18n: .. We have contracts with different publishers in different countries to sell and
.. i18n: .. distribute paper or electronic based versions of this book (translated or not)
.. i18n: .. in bookstores. This helps to distribute and promote the OpenERP product. It
.. i18n: .. also helps us to create incentives to pay contributors and authors using author
.. i18n: .. rights of these sales.
..

.. We have contracts with different publishers in different countries to sell and
.. distribute paper or electronic based versions of this book (translated or not)
.. in bookstores. This helps to distribute and promote the OpenERP product. It
.. also helps us to create incentives to pay contributors and authors using author
.. rights of these sales.

.. i18n: .. Due to this, grants to translate, modify or sell this book are strictly
.. i18n: .. forbidden, unless Tiny SPRL (representing Open Object Press) gives you a
.. i18n: .. written authorisation for this.
..

.. Due to this, grants to translate, modify or sell this book are strictly
.. forbidden, unless Tiny SPRL (representing Open Object Press) gives you a
.. written authorisation for this.

.. i18n: .. Many of the designations used by manufacturers and suppliers to distinguish their
.. i18n: .. products are claimed as trademarks. Where those designations appear in this book,
.. i18n: .. and Open Object Press was aware of a trademark claim, the designations have been
.. i18n: .. printed in initial capitals.
..

.. Many of the designations used by manufacturers and suppliers to distinguish their
.. products are claimed as trademarks. Where those designations appear in this book,
.. and Open Object Press was aware of a trademark claim, the designations have been
.. printed in initial capitals.

.. i18n: .. While every precaution has been taken in the preparation of this book, the publisher
.. i18n: .. and the authors assume no responsibility for errors or omissions, or for damages
.. i18n: .. resulting from the use of the information contained herein.
..

.. While every precaution has been taken in the preparation of this book, the publisher
.. and the authors assume no responsibility for errors or omissions, or for damages
.. resulting from the use of the information contained herein.

.. i18n: .. Published by Open Object Press, Grand Rosière, Belgium
..

.. Published by Open Object Press, Grand Rosière, Belgium
