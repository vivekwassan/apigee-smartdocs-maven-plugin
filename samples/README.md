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