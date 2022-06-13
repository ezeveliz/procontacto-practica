# procontacto-practica
Ejercicios de evaluación práctica para ProContacto

## Ejercicios

- [Ejercicio 2](#ejercicio-2)
- [Ejercicio 3](#ejercicio-3)
- [Ejercicio 4](#ejercicio-4)
- [Ejercicio 5](#ejercicio-5)
- [Ejercicio 6](#ejercicio-6)
- [Ejercicio 7](#ejercicio-7)

### Ejercicio 2
1. ¿Qué es un servidor HTTP?

   Un servidor HTTP es un componente de software que implementa el protocolo de transferencia HTTP, el mismo es una especie de contrato o interfaz que deben cumplir los distintos servicios web para poder comunicarse y entenderse entre ellos. Permite recibir y responder a distintas consultas hechas en el formato específico definido anteriormente. 
2. ¿Qué son los verbos HTTP? Mencionar los más conocidos
   
   Los verbos HTTP permiten definir distintas acciones a realizar sobre distintos recursos, como por ejemplo obtener los datos de una persona dado su ID, actualizar sus datos o eliminarla de un servicio.
   * GET: Obtiene el o los recursos pedidos, no debería generar efectos colaterales(actualización de datos o eliminaciones).
   * POST: Crea una nueva instancia del recurso dado con base en ciertos datos pasados por ejemplo en el body del request.
   * PUT: Permite actualizar los datos asociados a un recurso dado, se debe pasar el conjunto de datos completo asociado al mismo, ya que se persistirá lo que se reciba, si el recurso pasado no existía se creará uno nuevo.
   * PATCH: Permite actualizar los datos asociados a un recurso dado, a diferencia de PUT, no es necesario pasar todo el conjunto de datos, solo es necesario enviar los cambios.
   * DELETE: Elimina el recurso asociado a los datos pasados, por ejemplo, el ID del mismo.
3. ¿Qué es un request y un response en una comunicación HTTP? ¿Qué son los headers?

   En el contexto de una comunicación HTTP, un request es una solicitud hecha a un servidor, la misma puede utilizar cualquiera de los verbos descritos en el punto anterior, y la response es la respuesta originada por el servidor al request hecho anteriormente. Los headers son sencillamente un mecanismo que permite intercambiar información adicional entre el cliente y el servidor durante los requests y las responses.  
4. ¿Qué es un queryString? (En el contexto de una url)

   Un queryString es una manera de agregar datos en una URL, se escriben a continuación de un signo de pregunta(?) y se agregan de a pares clave/valor con un igual(=) entre ambos, si se quieren agregar multiples, se debe incrustar un ampersand(&) entre cada par clave/valor. 
5. ¿Qué es el responseCode? ¿Qué significado tiene los posibles valores devueltos?

   Un responseCode es un código que indica si un request dado se logró completar con éxito o no(y en este caso donde está el error), el mismo es parte de la response. Existen cinco tipos de responseCodes agrupados en las siguientes clases:
   * 100-199: Respuestas informativas
   * 200-299: Respuestas correctas
   * 300-399: Mensajes de redirección
   * 400-499: Errores en el cliente que produjo el request
   * 500-599: Errores en el servidor

   > Si se recibe un código que no pertenece a ninguna de estas cinco clases, el mismo no forma parte del standard y es propio del código del servidor. 
6. ¿Cómo se envía la data en un Get y cómo en un POST?
   
   En un GET, los datos viajan embebidos en la URL desde el cliente hacia el servidor, por ejemplo mediante un queryString, en el caso del POST, los mismos viajan en un campo del request llamado body, a diferencia de los requests GET, estos no pueden ser cacheados y no quedan en el historial del dispositivo.
7. ¿Qué verbo http utiliza el navegador cuando accedemos a una página?

   Al acceder a una página web, el navegador utiliza el verbo GET.
8. Explicar brevemente qué son las estructuras de datos JSON y XML dando ejemplo de estructuras posibles.

   Una estructura JSON es una estructura que sirve para el intercambio de datos, basada en un subset del lenguaje de programación JavaScript y formada básicamente por dos tipos de estructuras, siendo estas el array y pares clave/valor
```json
{
    "personas": [
       {
          "nombre": "Ezequiel",
          "edad": 27, 
          "mascotas": [
             {
                "animal": "gato"
             }
          ]
       },
       {
          "nombre": "Pepe",
          "edad": 30,
          "mascotas": []
       }
    ]
}
```
   Las estructuras XML buscan el mismo objetivo que las estructuras JSON, el intercambio de información, pero se construyen utilizando un lenguaje similar al HTML mediante etiquetas que se abren y cierran.
```xml 
<?xml version="1.0" encoding="UTF-8" ?>
<root>
  <personas>
    <nombre>Ezequiel</nombre>
    <edad>27</edad>
    <mascotas>
      <animal>gato</animal>
    </mascotas>
  </personas>
  <personas>
    <nombre>Pepe</nombre>
    <edad>30</edad>
    <mascotas/>
  </personas>
</root>
```
9. Explicar brevemente el estándar SOAP.
10. Explicar brevemente el estándar REST Full
11. ¿Qué son los headers en un request? ¿Para qué se utiliza el key Content-type en un header?

   Los headers son un mecanismo para enviar información del cliente al servidor en los requests y del servidor al cliente en las responses. Se forman utilizando un par clave/valor con dos puntos(:) entre ellos. El key Content-Type se utiliza para indicar el tipo de datos a recibir/enviar dependiendo de si se trata de un response o request, en el caso del primero indica por ejemplo el formato de video durante una descarga, en el caso de un request indica el tipo de dato enviado, por ejemplo un documento json.

[← Volver](#ejercicios)
### Ejercicio 3
1. Realizar un request GET a la siguiente [URL](https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json)

![Screenshot del sub punto 1](./assets/ejer-2-1.png)

2. Realizar un request POST a la URL anterior con el siguiente body:
```json
{
    "name": "Ezequiel",
    "email": "ezequiel.veliz@procontacto.com.mx"
}
```
![Screenshot del sub punto 2](./assets/ejer-2-2.png)

3. Realizar nuevamente un request GET a la [URL](https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json)

![Screenshot del sub punto 3](./assets/ejer-2-3.png)

4. ¿Qué diferencias se observan entre 1 y 3?
 
    Como se puede observar, al realizar el segundo request GET, el mismo retorna además del contenido original, el contenido del body del request POST del segundo paso.   

[← Volver](#ejercicios)
### Ejercicio 4

URL del perfil de Trailhead: [https://trailblazer.me/id/ezeveliz](https://trailblazer.me/id/ezeveliz)

[← Volver](#ejercicios)
### Ejercicio 5

1. Lead

   Un objeto Lead representa una posibilidad, por ejemplo un posible contacto, una posible cuenta, una posible oportunidad de venta.
   
   Utilizando el Schema Builder no se visualizan, pero en la documentación indica que este objeto posee tres relaciones Lookup con los objetos Account, Contact y Opportunity, estos campos se setean una vez que el objeto Lead haya sido convertido.
   * Campos: ActionCadenceAssigneeId, ActionCadenceId, ActivityMetricId, Address, AnnualRevenue, City, CleanStatus, Company, CompanyDunsNumber, ConnectionReceivedId, ConnectionSentId, ConvertedAccountId, ConvertedContactId, ConvertedDate, ConvertedOpportunityId, Country, CountryCode, CurrencyIsoCode, Description, Division, Email, EmailBouncedDate, EmailBouncedReason, Fax, FirstCallDateTime, FirstEmailDateTime, FirstName, HasOptedOutOfEmail, HasOptedOutOfFax, GeocodeAccuracy, IndividualId, Industry, IsConverted, IsDeleted, IsUnreadByOwner, Jigsaw, LastActivityDate, LastName, LastReferencedDate, LastViewedDate, LeadSource, MasterRecordId, MiddleName, MobilePhone, Name, NumberOfEmployees, OwnerId, PartnerAccountId, Phone, PhotoUrl, PostalCode, Rating, RecordTypeId, Salutation, ScoreIntelligenceId, State, StateCode, Status, Street, Suffix, Title y Website.
2. Account

   El objeto Account representa una cuenta en el negocio, la misma puede ser una organización o una persona relacionada con el mismo, como por ejemplo clientes, competidores y compañeros.
   
   Posee una única relación, y la misma es una relación Master-Detail contra sí mismo para indicar jerarquía entre diferentes cuentas, luego, existen múltiples relaciones Lookup pero todas son desde otros objetos a este, como por ejemplo de Contact, Quote, Opportunity, etc.
   * Campos: AccountNumber, AccountSource, AnnualRevenue, BillingAddress, BillingCity, BillingCountry, BillingCountryCode, BillingGeocodeAccuracy, BillingPostalCode, BillingState, BillingStateCode, BillingStreet, ChannelProgramName, ChannelProgramLevelName, CleanStatus, ConnectionReceivedId, ConnectionSentId, Description, DunsNumber, Fax, HasOptedOutOfEmail, IsCustomerPortal, IsDeleted, IsPartner, IsPersonAccount, Jigsaw, LastActivityDate, LastReferencedDate, LastViewedDate, MasterRecordId, NaicsCode, NaicsDesc, Name, NumberOfEmployees, OperatingHoursId, OwnerId, Ownership, ParentId, PersonIndividualId, Phone, PhotoUrl, Rating, RecordTypeId, Salutation, ShippingAddress, ShippingCity, ShippingCountry, ShippingCountryCode, ShippingGeocodeAccuracy, ShippingPostalCode, ShippingState, ShippingStateCode, ShippingStreet, Sic, SicDesc, Site, TickerSymbol, Tradestyle, Type, Website, YearStarted, FirstName, LastName, MiddleName, PersonAssistantName, PersonAssistantPhone, PersonBirthDate, PersonContactId, PersonDepartment, PersonEmail, PersonEmailBouncedDate, PersonEmailBouncedReason, PersonHasOptedOutOfEmail, PersonHomePhone, PersonLeadSource, PersonMailingAddress, PersonMailingCity, PersonMailingGeocodeAccuracy, PersonMailingLatitude, PersonMailingLongitude, PersonMailingStreet, PersonMobilePhone, PersonOtherLatitude, PersonOtherLongitude, PersonOtherPhone, PersonOtherStreet, PersonTitle y Suffix.
3. Contact

   El objeto Contact representa una persona individual asociada a una cuenta(objeto Account)
   
   Este Objeto posee una relación consigo mismo para el caso en el que dos contactos hayan sido unidos(merge) y con la cuenta a la que pertenece, al mismo tiempo hay múltiples otros objetos que se relacionan con este como por ejemplo Quote, Lead o Asset.
   * Campos: AccountId, AssistantName, AssistantPhone, Birthdate, CanAllowPortalSelfReg, CleanStatus, ConnectionReceivedId, ConnectionSentId, Department, Description, DoNotCall, Email, EmailBouncedDate, EmailBouncedReason, Fax, FirstCallDateTime, FirstName, HasOptedOutOfEmail, HasOptedOutOfFax, HomePhone, IndividualId, IsDeleted, IsEmailBounced, IsPersonAccount, Jigsaw, LastActivityDate, LastName, LastReferencedDate, LastViewedDate, LeadSource, MailingAddress, MailingCity, MailingState, MailingCountry, MailingPostalCode, MailingStateCode, MailingCountryCode, MailingStreet, MailingGeocodeAccuracy, MasterRecordId, MiddleName, MobilePhone, Name, OtherAddress, OtherCity, OtherCountry, OtherPostalCode, OtherState, OtherCountryCode, OtherStateCode, OtherGeocodeAccuracy, OtherPhone, OtherStreet, OwnerId, Phone, PhotoUrl, RecordTypeId, ReportsToId, Salutation, Suffix y Title.
4. Opportunity

   El objeto Opportunity representa una venta, o una posible venta.
   
   Este objeto posee una relación Master-Detail con el objeto Quote, ya que en este están almacenados los posibles listados de productos a vender y posibles descuentos, Luego, también está relacionado con el Price Book porque del mismo se obtienen los precios de los artículos, también con Account para saber a quién le pertenece la oportunidad, con el Objeto Lead que origino la oportunidad. 
   * Campos: AccountId, AgeInDays, Amount, CampaignId, CloseDate, ConnectionReceivedId, ConnectionSentId, ContactId, ContractId, CurrencyIsoCode, Description, ExpectedRevenue, Fiscal, FiscalQuarter, FiscalYear, ForecastCategory, ForecastCategoryName, HasOpenActivity, HasOpportunityLineItem, HasOverdueTask, IqScore, IsClosed, IsDeleted, IsExcludedFromTerritory2Filter, IsPriorityRecord, IsSplit, IsWon, LastActivityDate, LastActivityInDays, LastAmountChangedHistoryId, LastCloseDateChangedHistoryId, LastReferencedDate, LastStageChangeDate, LastStageChangeInDays, LastViewedDate, LeadSource, Name, NextStep, OwnerId, PartnerAccountId, Pricebook2Id, PricebookId, Probability, PushCount, RecordTypeId, StageName, SyncedQuoteID, Territory2Id, TotalOpportunityQuantity y Type.
6. Product

   El objeto Product representa un producto que vende la compañía.

   Este objeto no está relacionado con otros, sino que otros están relacionados con él, como por ejemplo Case y Asset. Se relaciona mediante una tabla intermedia con el objeto Price Book y con el objeto Opportunity.
   * Campos: BillingPolicyId, CanUseQuantitySchedule, CanUseRevenueSchedule, ConnectionReceivedId, ConnectionSentId, CurrencyIsoCode, Description, DisplayUrl, ExternalDataSourceId, ExternalId, Family, IsActive, IsArchived, IsDeleted, LastReferencedDate, LastViewedDate, Name, NumberOfQuantityInstallments, NumberOfRevenueInstallments, ProductClass, ProductCode, QuantityInstallmentPeriod, QuantityScheduleType, QuantityUnitOfMeasure, RecalculateTotalPrice, RevenueInstallmentPeriod, RevenueScheduleType, StockKeepingUnit, Type y TaxPolicyId.
7. Price Book

   El objeto Price Book representa una lista de precios de los distintos productos que vende la organización, pueden existir diferentes dedicadas a diferentes propósitos, como por ejemplo dedicadas a distintos canales de venta, mercados, con distintos descuentos, etc. La entrada de cada lista de precios se encuentra almacenada en el objeto Price Book Entry.
   
   Está relacionado con el objeto: Opportunity.
   * Campos: Description, IsActive, IsArchived, IsDeleted, IsStandard, LastReferencedDate, LastViewedDate, Name, ValidFrom y ValidTo.
8. Quote

   El objeto Quote hace de detail en una relación Master-Detail con el objeto Opportunity, el mismo es una colección de productos o servicios, con los precios propuestos, posibles descuentos, subtotales y totales, se pueden crear desde el objeto Opportunity y luego ser enviados como PDF al potencial cliente.

   Está relacionado con los objetos: Account, Contact, Opportunity, Pricebook.
   * Campos: AccountId, AdditionalAddress, AdditionalCity, AdditionalCountry, AdditionalCountryCode, AdditionalLatitude, AdditionalLongitude, AdditionalName, AdditionalPostalCode, AdditionalState, AdditionalStateCode, AdditionalStreet, BillingAddress, BillingCity, BillingCountry, BillingCountryCode, BillingLatitude, BillingLongitude, BillingName, BillingPostalCode, BillingState, BillingStateCode, BillingStreet, CalculationStatus, CanCreateQuoteLineItems, ContactId, ContractId, CurrencyIsoCode, Description, Discount, Email, ExpirationDate, Fax, IsSyncing, LastReferencedDate, LastViewedDate, LineItemCount, Name, OpportunityId, Phone, Pricebook2Id, QuoteNumber, QuoteToAddress, QuoteToCity, QuoteToCountry, QuoteToLatitude, QuoteToLongitude, QuoteToName, QuoteToPostalCode, QuoteToState, QuoteToStreet, RecordTypeID, ShippingAddress, ShippingCity, ShippingCountry, ShippingCountryCode, ShippingHandling, ShippingLatitude, ShippingLongitude, ShippingName, ShippingPostalCode, ShippingState, ShippingStateCode, ShippingStreet, Status, Subtotal, Tax, TotalPrice, TotalPriceWithTax y TotalTaxAmount. 
9. Asset

   El objeto Asset representa un artículo de valor comercial como por ejemplo un producto vendido por la compañía o un competidor, que un cliente compró. Poseen número de serie, fecha de compra y otros datos relacionados con la venta individual. Se pueden crear árboles de jerarquía para representar assets compuestos por otros assets.

   Está relacionado con los objetos: Account, Contact, Asset(en caso de assets compuestos existen 2 referencias, una apunta a su padre directo y la otra apunta al asset que representa la raíz del árbol).
   * Campos: AccountId, AssetLevel, AssetProvidedById, AssetServicedById, Availability, AverageUptimePerDay, ConsequenceOfFailure, ContactId, CurrentAmount, CurrentLifecycleEndDate, CurrentMrr, CurrentQuantity, Description, DigitalAssetStatus, ExternalIdentifier, HasLifecycleManagement, InstallDate, IsCompetitorProduct, IsInternal, LastReferencedDate, LastViewedDate, LifecycleEndDate, LifecycleStartDate, LocationId, ManufactureDate, Name, OwnerId, ParentId, Price, Product2Id, ProductCode, ProductDescription, ProductFamily, PurchaseDate, Quantity, Reliability, RenewalTerm, RenewalTermUnit, RootAssetId, SerialNumber, Status, StatusReason, StockKeepingUnit, SumDowntime, SumUnplannedDowntime, TotalLifecycleAmount, UptimeRecordEnd, UptimeRecordStart, UsageEndDate y Uuid.

10. Case

    El objeto Case representa algún problema, pregunta o retroalimentación(o comentario) y sus datos asociados como puede ser el tiempo que tarda en resolverse, comentarios, la cuenta relacionada que lo originó, el encargado del mismo, las actividades necesarias para solucionarlo o los métodos de contacto con el que lo originó.

    Está relacionado con los objetos: Account, Contact, Case(para el caso en que se unan(merge) dos cases diferentes o en el caso de que uno esté relacionado con otro)
     * Campos: AccountId, BusinessHoursId, Comments, CaseNumber, ClosedDate, CommunityId, ConnectionReceivedId, ConnectionSentId, ContactEmail, ContactFax, ContactId, ContactMobile, ContactPhone, CreatorFullPhotoUrl, CreatorName, CreatorSmallPhotoUrl, Description, FeedItemId, HasCommentsUnreadByOwner, HasSelfServiceComments, IsClosed, IsClosedOnCreate, IsDeleted, IsEscalated, IsSelfServiceClosed, IsStopped, IsVisibleInSelfService, Language, LastReferencedDate, LastViewedDate, MasterRecordId, Origin, OwnerId, ParentId, Priority, QuestionId, Reason, RecordTypeId, SlaStartDate, SourceId, Status, StopStartDate, Subject, SuppliedCompany, SuppliedEmail, SuppliedName, SuppliedPhone y Type.

11. Article

   Con respecto a este objeto, encontré referencias al mismo hasta la API versión 44.0(a partir de la misma se encuentra como "Salesforce Knowledge Objects") y no sería un objeto único, sino un conjunto de objetos(donde el objeto principal es KnowledgeArticle y se relaciona a través de una tabla intermedia llamada CaseArticle con el objeto Case) para representar información sobre los productos y servicios de la compañía y hacerlos disponibles en una base de conocimientos(KB). 
   
   Permite versionar la información disponible en los mismos, categorizarla según el tema al que hace referencia, asignarla a distintos canales(clientes, KB pública, etc.) y utilizar un ciclo de publicación con distintos estados, como por ejemplo Draft para indicar que aún está en construcción, Online para indicar que está publicado y Archived cuando su contenido ya no aplica. 

![Salesforce DER](./assets/ejer-5.png)

> Notas:
>  * El diagrama fue realizado utilizando tanto el Schema Builder del Playground como la documentación de referencia de los objetos standard de la API versión 55.0.
>  * Las relaciones que poseen una leyenda del estilo "XN" indican que poseen N relaciones en el mismo sentido de un objeto dado a otro, como por ejemplo entre Account y Asset. 
>  * El objeto Quote no se encontraba por default en el Schema Builder, tuve que activarlo desde el Setup del Playground.
>  * La flecha de color rojo entre Account y Account, y entre Opportunity y Quote, representa una relación Master-Detail, el resto son relaciones Lookup.

[← Volver](#ejercicios)
### Ejercicio 6
[← Volver](#ejercicios)
### Ejercicio 7
[← Volver](#ejercicios)