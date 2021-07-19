# CrudFrontend

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 11.0.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.

Como gerar o certificado p12

Criar a chave privada<br>
openssl genrsa -out api-certificate.pem 2048

Gerar o csr<br>
openssl req -new -sha256 -key api-certificate.pem -out api-certificate.csr

Comando pra gerar o arquivo pem<br>
openssl req -x509 -sha256 -days 365 -key api-certificate.pem -in api-certificate.csr -out api-certificate.pem

Comando pra gerar o p12<br>
openssl pkcs12 -export -out api-identity.p12 -inkey key.pem -in api-certificate.pem

Comando pra gerar o arquivo crt a partir da pasta onde estiver o certificado p12<br>
openssl pkcs12 -in api-certificate.p12 -clcerts -nokeys -out api-certificate.crt

Comando pra gerar o arquivo key a partir da pasta onde estiver o certificado p12<br>
openssl pkcs12 -in api-certificate.p12 -nocerts -nodes -out api-certificate.key
