
#### @ResponseStatus(value = HttpStatus.INTERNAL_SERVER_ERROR, reason = MyReasonsClass.REASON_OF_ERROR)
If this exception is thrown while processing an HTTP request, then the response will include the HTTP status specified in this annotation.
for translation we use in the frontend part the REASON_OF_ERROR and a usecae to translate the message with i18next

#### creating custom annottions

Class Level Annotation: The first step toward creating a custom annotation is to declare it using the @interface keyword 
&nbsp;&nbsp;The next step is to add **meta-annotations** to specify the scope and the **target** of our custom annotation:
&nbsp;&nbsp;&nbsp;&nbsp;@Retention(RetentionPolicy.RUNTIME)
&nbsp;&nbsp;&nbsp;&nbsp;@Target(ElementType.Type)
&nbsp;&nbsp;&nbsp;&nbsp;public @iterface MyAnnot{}

Field Level Annotatio
