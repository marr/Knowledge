# HTTP

## Learn more

- https://httpwg.org/specs/.

## Retrieve data

```
GET
```

## Submit data

```
POST
```

## Replace data

```
PUT
```

## Remove data

```
DELETE
```

## Indicate the result of a request in the response

```
Status code
```

- 100–199 for informational responses.
- 200–299 for successful responses.
- 300–399 for redirects.
- 400–499 for client errors.
- 500–599 for server errors.
- `200` is a catchall for success.
- `404` means the requested resource is not available.
- `403` means the requester does not have permission to access the requested resource.
- `500` is a catchall for server-side errors.

## Include additional information in headers of requests or responses

```
Name: value
```

For example:

```
Cache-Control: max-age=600
Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l
Age: 24
```
