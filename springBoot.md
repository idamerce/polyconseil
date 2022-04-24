
### @ResponseStatus(value = HttpStatus.INTERNAL_SERVER_ERROR, reason = MyReasonsClass.REASON_OF_ERROR)
If this exception is thrown while processing an HTTP request, then the response will include the HTTP status specified in this annotation.
for translation we use in the frontend part the REASON_OF_ERROR and a usecae to translate the message with i18next

### creating custom annottions

Class Level Annotation: The first step toward creating a custom annotation is to declare it using the @interface keyword 
 &nbsp;&nbsp;The next step is to add **meta-annotations** to specify the scope and the **target** of our custom annotation <br />
 As we can see, our first annotation has runtime visibility, and we can apply it to types (classes). Moreover, it has no methods, and thus serves as a simple marker to mark classes that can be serialized into JSON: <br />
* &nbsp;&nbsp;&nbsp;&nbsp;@Retention(RetentionPolicy.RUNTIME)
* &nbsp;&nbsp;&nbsp;&nbsp;@Target(ElementType.Type)
* &nbsp;&nbsp;&nbsp;&nbsp;public @iterface MyAnnot{}

Field Level Annotatio: @Target(ElementType.FIELD) 
Method Level Annotation: @Target(ElementType.METHOD)

### Jackson – Custom Serializer
`@JsonSerialize(using = AlienSerializer.class)
public class Alien {}`
Simply put, we'll have to define a custom Serializer for our Alien objects:

public class AlienSerializer extends StdSerializer< Alien > {
 
    public AlienSerializer() { this(null);}
 
    public AlienSerializer(Class<Alien> t) { super(t);}
 
    @Override
    public void serialize(
      Item value, JsonGenerator jgen, SerializerProvider provider) 
      throws IOException, JsonProcessingException {
        jgen.writeStartObject();
        jgen.writeNumberField("id", value.id);
        jgen.writeStringField("AlienName", value.AlienName);
        jgen.writeNumberField("AlienShip", value.ship.id);
        jgen.writeEndObject();
    }
 }
 
