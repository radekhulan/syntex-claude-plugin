---
name: orders
description: Read the connected customer's own orders and order details from SYNTEX Croatia at syntex.hr when the user requests their order history.
---

Use list_my_orders on plugin:syntex-hr:syntex and then get_my_order with an exact orderId from that result. Retail order IDs are strings; AVYX can return ERP GUIDs. Never substitute a displayed reference or fabricate an ID. Request only the order information needed for the user's question.

Stay within the connected account and market. Do not guess another customer's order IDs, switch identities, or use an administrative connector. If the user requests someone else's private order, explain that the connection only exposes their authorized account data.

Describe stored statuses accurately. A fulfilled ERP order does not by itself prove payment or delivery. These tools read stored order data and do not query a payment gateway. If evidence is missing, say so. A failed lookup is not evidence that an order never existed; report the returned error or scope limitation.

Do not cancel or change orders, arrange refunds, make payments, or modify the catalog. Those actions are not provided by this customer order workflow. Never ask for passwords, card details or authentication tokens in chat.
