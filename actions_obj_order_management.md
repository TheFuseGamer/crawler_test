# Salesforce Order Management Actions

Manage, fulfill, and service orders in flows with Salesforce Order
   Management.

For more information about using Order Management actions in flows, see [Salesforce Order Management Flow Core
     Actions](https://help.salesforce.com/HTViewHelpDoc?id=flow_ref_elements_om_actions_list.htm&amp;language=en_US "HTML (New Window)") in Salesforce Help.

These actions are available in API version 48.0 and later.

Your org must have a Salesforce Order Management license.

## Supported REST HTTP Methods

      - URI

          - Get a specific Order Management action:

          - <samp class="codeph nolang"><samp class="codeph nolang">/v<var class="keyword varname">XX.X</var>/</samp>actions/standard/<var class="keyword varname">om_action_name</var></samp>

      - Formats

          - JSON, XML

      - HTTP Methods

          - GET

      - Authentication

          - <samp class="codeph nolang">Authorization: Bearer <var class="keyword varname">token</var></samp>

      - Notes

          - Order Management actions are intended for use in flows. The standard actions URI can only
       be used to get information about them. To use these actions in code, call the corresponding
       Connect REST API endpoints or Apex ConnectApi methods. For more information, see [Order Management
        Resources](https://developer.salesforce.com/docs/atlas.en-us.230.0.chatterapi.meta/chatterapi/connect_resources_order_management_resources.htm "HTML (New Window)") in the <cite class="cite">Connect REST API Developer Guide</cite> and [ConnectApi Namespace](https://developer.salesforce.com/docs/atlas.en-us.230.0.apexcode.meta/apexcode/apex_classes_connect_api.htm "HTML (New Window)") in
       the <cite class="cite">Apex Developer Guide</cite>.

          - In flows, Order Management action inputs and outputs use Apex-defined variables that map
       to input and output classes in the ConnectApi namespace.