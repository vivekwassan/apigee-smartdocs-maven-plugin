# Samples

## DevPortal

Create models and import OpenAPI specs to a developer portal instance
```
/samples/DevPortal
```

This project demonstrates use of apigee-smartdocs-maven-plugin to create models and import OpenAPI specs to a developer portal. The example project performs a data import defined in pom.xml

**Note that to utilize this example, you will need a working developer portal instance with the [smartdocs_service module](https://github.com/apigeecs/smartdocs_service) installed and enabled.**

To use, edit samples/DevPortal/pom.xml, and update portal values.

      <portal.username>${pusername}</portal.username><!-- Username for the developer portal. -->
      <portal.password>${ppassword}</portal.password><!-- Password for the developer portal. -->
      <portal.directory>${pdirectory}</portal.directory><!-- Directory whered OpenAPI specs are accessible. -->
      <portal.url>${purl}</portal.url><!-- URL of the developer portal. -->
      <portal.path>${ppath}</portal.path><!-- Servies path defined in the developer portal. -->
      <portal.format>json</portal.format><!-- Format of the OpenAPI specs. -->

To run jump to samples project `cd /samples/DevPortal` and run 

`mvn install -Pdev -Dapigee.smartdocs.config.options=create`


Add field data to a model in a developer portal instance
```
/samples/DevPortal
```

This project demonstrates use of apigee-smartdocs-maven-plugin to add field data to a model in a developer portal. The example project performs a data import defined in pom.xml

**Note that to utilize this example, you will need a working developer portal instance with the [smartdocs_service module](https://github.com/apigeecs/smartdocs_service) installed and enabled. You will also need the standard taxonomy endpoints enabled and accessible**

See `Create models and import OpenAPI specs` above for info on how to set up the pom.xml to access the Developer Portal.

To use, edit samples/DevPortal/shared-pom.xml, and update portal values.

    <configuration>
        <portal.model.vocabulary>${model_vocabulary}</portal.model.vocabulary>
        <portal.model.fields>
            <company>
                <path>contact|company</path>
                <field>field_company</field>
            </department>
        </portal.model.fields>
    </configuration>

The path value signifies the path to data stored within the info object. 
The pipe character can be used to traverse into sub-items. For instance, with a OpenAPI document containing  { "info": { "contact": { "company": "Google" } } }, you could be access the data by setting the path to contact|company.
In the example above, "Google" would be mapped to the field_company field within the model related to the OpenAPI document definition.

To run jump to samples project `cd /samples/DevPortal` and run 

`mvn install -Pdev -Dapigee.smartdocs.config.options=create`