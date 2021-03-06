## Examples and further information

This project shows how to generate code from provided [OpenAPI 3 specification](https://swagger.io/specification/). More examples and documentation at [oapi-codegen](https://github.com/deepmap/oapi-codegen). You can display provided API in [the online Swagger UI editor](https://editor.swagger.io/).


## Run project
1. Clone project
2. Build project
```bash
go build .
```
3. Run generated *.exe file


## Setup similar project

1. Initialize go project
2. Import oapi-codegen
```bash
go get github.com/deepmap/oapi-codegen/cmd/oapi-codegen
```
3. Create API directory (optional, feel free to store it wherever you want, remember to use proper oapi-codegen commands)
```bash
mkdir api
```
4. Generate code
```bash
# GENERATE 'ALL-IN-ONE'
oapi-codegen --package api ./store-api.yaml > api/store.gen.go

# GENERATE SEPARATED TYPES AND SERVER
oapi-codegen --config=types.cfg.yaml ./store-api.yaml
oapi-codegen --config=server.cfg.yaml ./store-api.yaml

# OR
oapi-codegen --package api --generate types ./store-api.yaml > api/store-types.gen.go
oapi-codegen --package api --generate chi-server ./store-api.yaml > api/store-server.gen.go
```
5. Build & run project


## Generate changes without manual corrections

1. Open [store-api.yaml](https://github.com/bartekstrach/OpenAPIChi/blob/master/store-api.yaml) file
2. Uncomment lines 147-149
```yaml
age:
  type: integer
  format: int32
```
3. Generate types
```bash
oapi-codegen --config=types.cfg.yaml ./store-api.yaml
# OR
oapi-codegen --package api --generate types ./store-api.yaml > api/store-types.gen.go
```
4. Adjust business logic - open [store.go](https://github.com/bartekstrach/OpenAPIChi/blob/master/api/store.go) file
5. Uncomment line 86
```go
pet.Age = newPet.Age
```
6. Build & run project
