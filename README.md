## Examples and further information

This project shows how to generate code from provided [OpenAPI 3 specification](https://swagger.io/specification/). More examples and documentation at [oapi-codegen](https://github.com/deepmap/oapi-codegen). You can display provided API in [the online Swagger UI editor](https://editor.swagger.io/).


## Setup project:

1. Import oapi-codegen
```bash
go get github.com/deepmap/oapi-codegen/cmd/oapi-codegen
```
2. Create API directory (optional, feel free to store it wherever you want, remember to use proper oapi-codegen commands)
```bash
mkdir api
```
3. Generate code
```bash
# GENERATE 'ALL-IN-ONE'
oapi-codegen --package api ./store-api.yaml > api/store.gen.go

# GENERATE SEPARATED TYPES AND SERVER
oapi-codegen --config=types.cfg.yaml ./store-api.yaml
oapi-codegen --config=server.cfg.yaml ./store-api.yaml

# OR
oapi-codegen --package api --generate types ./store-api.yaml > store-types.gen.go
oapi-codegen --package api --generate chi-server ./store-api.yaml > store-server.gen.go
```
