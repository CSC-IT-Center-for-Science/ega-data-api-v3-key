# EGA.Data.API.v3.KEY

This is a standalone Encryption Key server. It is available via EUREKA using the service name `"KEY"`.

Dependency: 
* CONFIG (`https://github.com/elixir-europe/ega-data-api-v3-config`). The `'bootstrap-blank.properties'` file must be modified to point to a running configuration service, which will be able to serve the `application.properties` file for this service `KEY`
* EUREKA (`https://github.com/elixir-europe/ega-data-api-v3-eureka`). This is not required for this service by itself; however, the RES service will contact this KEY service via EUREKA. Therefore this service expects a running EUREKA service and registers itself with it. 

Provides: 
* RES: requests encryption and decryption keys from this service

This service provides a very basic abstraction to handle encryption keys. Each installation will have to assess the security needs for this service. It should run in a private area shielded from outside access. Only RES should access this service.

This service uses a separate configuration XML to describe the keys used.

This service can be used (developed into) either as a proxy to existing key management systems, or into its own key management solution.

### Todos

 - Write Tests
 - Address security

