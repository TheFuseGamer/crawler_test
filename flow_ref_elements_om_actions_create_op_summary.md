# Flow Core Action for Order Management: Create Order Payment
      Summary

Create an order payment summary for a payment authorization or
      payments that use the same payment method and are attached to the same order
    summary.

| Available in: Lightning Experience |
| --- |
| Available in: **Enterprise**, **Unlimited**, and **Developer**
                Editions with Salesforce Order Management |

Drag an Action element onto the canvas. Select the **Order Management**         category, and search for **Create Order Payment Summary**. 

## Set Input Values

Use values from earlier in the flow to set the inputs.
      Include at least one payment authorization or list of payments; you don’t need both.

| Input Parameter | Description |
| --- | --- |
| Order Payment Summary Create Input | This input is an Apex-defined variable of class [ConnectApi.CreateOrderPaymentSummaryInputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_input_create_order_payment_summary.htm).<br>The variable                   includes these fields:<br>
<ul class="ul bulletList">
                  <li class="li">
<span class="keyword parmname">orderSummaryId</span> — Reference to the order summary
                    associated with the payments. In orgs with the multicurrency feature enabled,
                    the order payment summary inherits the <span class="keyword parmname">ISO Currency</span> value
                    from the order summary.</li>

                  <li class="li">
<span class="keyword parmname">paymentAuthorizationId</span> — Reference to the payment
                    authorization to associate with the summary.</li>

                  <li class="li">
<span class="keyword parmname">paymentIds</span> — List of IDs of the payments to
                    associate with the summary.</li>

                </ul> |

## Store Output Values

| Output Parameter | Description |
| --- | --- |
| Order Payment Summary Output | This value is an Apex-defined variable of class [ConnectApi.CreateOrderPaymentSummaryOutputRepresentation](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_connectapi_output_create_order_payment_summary_output.htm).<br>The                     orderPaymentSummaryId field contains the ID of the created                   order payment summary. |

## Usage

To set up the Order Payment Summary Create Input for payments, first use Assignment         elements to add the payment IDs to a list of strings variable. Then use that variable in the         action input.