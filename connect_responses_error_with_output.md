# Error with Output

Contains extra information about errors. In rare cases, an error message isn't enough to
  describe the reason for a failure. For example, when a conflicting precondition exists, the error
  result can include the information about the cause of the conflict.

| Property | Type | Description | Filter Group and Version | Available Version |
| --- | --- | --- | --- | --- |
| <samp class="codeph nolang">enhancedErrorType</samp> | String | Indicates the type of the <samp class="codeph nolang">output</samp> property. This
       value is either <samp class="codeph nolang">null</samp> or: <ul class="ul bulletList">
        <li class="li">
<samp class="codeph nolang">GroupMembershipRequestError</samp>–A nested Group Membership Request.</li>

       </ul> | Small, 39.0 | 39.0 |
| <samp class="codeph nolang">message</samp> | String | Description of the error | Small, 29.0 | 27.0 |
| <samp class="codeph nolang">output</samp> | Any response body | The response body returned by the requested resource. For example, if a successful request
       returns a Like response body but an error triggers the Error with Output response body, the
       value of the <samp class="codeph nolang">output</samp> property is a Like response
       body. | Small, 29.0 | 27.0 |