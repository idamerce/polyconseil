
#### @ResponseStatus(value = HttpStatus.INTERNAL_SERVER_ERROR, reason = MyReasonsClass.REASON_OF_ERROR)
If this exception is thrown while processing an HTTP request, then the response will include the HTTP status specified in this annotation.
for translation we use in the frontend part the REASON_OF_ERROR and a usecae to translate the message with i18next

