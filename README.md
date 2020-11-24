Examples and further information
https://github.com/deepmap/oapi-codegen

<!-- IMPORT OAPI-CODEGEN -->
go get github.com/deepmap/oapi-codegen/cmd/oapi-codegen

<!-- CREATE API DIRECTORY -->
mkdir api

<!-- GENERATE 'ALL-IN-ONE' -->
oapi-codegen --package api ./store-api.yaml > api/store.gen.go

<!-- GENERATE SEPARATED TYPES AND SERVER -->
oapi-codegen --config=types.cfg.yaml ./store-api.yaml
oapi-codegen --config=server.cfg.yaml ./store-api.yaml
<!-- OR -->
<!-- oapi-codegen --package api --generate types ./store-api.yaml > store-types.gen.go -->
<!-- oapi-codegen --package api --generate chi-server ./store-api.yaml > store-server.gen.go -->

<!-- Online Swagger UI Editor -->
https://editor.swagger.io/