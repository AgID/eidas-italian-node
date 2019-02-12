# Connessione all'ambiente di Quality Assurance

Il Nodo eIDAS italiano - nel seguito _Nodo_ - viene riconosciuto dalla
federazione SPID come un _Identity Provider_ (IdP).
Per questo motivo, il processo per connettere il proprio _Service Provider_ (SP) al Nodo
segue le stesse regole e gli stessi passi definiti in SPID.

Nel seguito sono riportate le informazioni necessarie per connettere
un SP SPID al Nodo, nell'ambiente di _Quality Assurance_ (QA).

**NOTA:** Gli aspetti grafici e di UX relativi all'integrazione non sono
oggetto di questa guida.

## Informazioni IdP "eIDAS"

L'IdP implementato dal Nodo nell'ambiente di QA è riconosciuto all'interno della federazione SPID
con il seguente `entityID`

    https://sp-proxy.pre.eid.gov.it/spproxy/idpit

I relativi metadata sono disponibili al seguente URL

    https://sp-proxy.pre.eid.gov.it/spproxy/idpitmetadata

L'integrità dei metadata può essere verificata utilizzando il seguente
certificato (self-signed).

```
-----BEGIN CERTIFICATE-----
MIID+DCCAuCgAwIBAgIJAOyLMGckjRLWMA0GCSqGSIb3DQEBCwUAMIGrMQswCQYDVQQGEwJJVDEt
MCsGA1UECgwkQWdlbnppYSBwZXIgbCdJdGFsaWEgRGlnaXRhbGUgLSBBZ0lEMSwwKgYDVQQLDCNG
SUNFUCBQcmUtcHJvZHVjdGlvbiBJbmZyYXN0cnVjdHVyZTE/MD0GA1UEAww2UHVibGljIEFkbWlu
aXN0cmF0aW9uIFNQIFBST1hZIFNBTUwgTWV0YWRhdGEgU2lnbmF0dXJlMB4XDTE4MTAwNTE5NTc0
OVoXDTI4MTAwMjE5NTc0OVowgasxCzAJBgNVBAYTAklUMS0wKwYDVQQKDCRBZ2VuemlhIHBlciBs
J0l0YWxpYSBEaWdpdGFsZSAtIEFnSUQxLDAqBgNVBAsMI0ZJQ0VQIFByZS1wcm9kdWN0aW9uIElu
ZnJhc3RydWN0dXJlMT8wPQYDVQQDDDZQdWJsaWMgQWRtaW5pc3RyYXRpb24gU1AgUFJPWFkgU0FN
TCBNZXRhZGF0YSBTaWduYXR1cmUwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDhGMIP
FELLzhPajFq477K+5jezFfEei0KVRDQRz3i9mF5wNUQRozuPaHgKBpXuA9T3Dw22hTVLf8bA94rM
pNGDZIiLI57HnqdxQBU78KWRKHJL/D5Xe0AexCVYnHlvnVanLMWTnnZDMdIPQP8LvG3yr5lLQCp0
VaTbG+ucUceur0j+cqm30IHergvQyU+5D0Ra8snw/tx+TDr0l38mdxYxpxmQZCgwG5oQ6N63P7zo
plZseJLNucYihmvhMX+nWl/v8kyTPAlBu3AtFOumO3gRtDheHLDuCY8SEsrhrmfiI/FG6yn75lgQ
kEkYceQXB/8IWC6qCuJfr7ASyvIM1zpvAgMBAAGjHTAbMAwGA1UdEwEB/wQCMAAwCwYDVR0PBAQD
AgbAMA0GCSqGSIb3DQEBCwUAA4IBAQAixTJtiM1Cy1YeT4V+dR9xqBpJYteLnD9z/R7GmYK5m+6g
Kxi5IZFZbZghMQ0pVNpaSwPDsf4/2TaChCtGwFl/RWf7ekM9xKsbaHBeJXE4Ap/t2SiEle89cApo
pMFGwVZ8/VVSybWYVxjw7Y21vzr4aoc7VXzcd4PGo0M6E0t2OkEIhSekxFE6wvplIsaJAK7fSTNe
tZZHVeriKP0tBXlslnk3rZJQNm7uy3JS35BWxw9RCLlpycIRxwAZrWhfAjYfF2VMHBJaUpsieS2u
tqVVAr7fWAIZk8+UJhsJ7Kb+IuRgbDX3BCUtNwvTVn6aREN+6U2pyId0dqmdCrse/Uq7
-----END CERTIFICATE-----
```

## Informazioni da comunicare ad AgID

Il gestore del SP dovrà comunicare ad AgID le seguenti informazioni

* Metadata (URL o file) del proprio SP
* Certificato utilizzato per firmare i metadata
* Certificato utilizzato per firmare i messaggi SAML
