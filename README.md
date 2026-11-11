# Operator Network APIs (CAMARA)

The network capabilities mobile operators expose to developers -- verifying a phone number, checking for a SIM swap, verifying or retrieving a device's location, its reachability and roaming status, matching KYC details, and requesting quality on demand. The shape is owned by the GSMA Open Gateway CAMARA project, so this context publishes CAMARA's own objects and measures who implements them.

**A reference context.** The shape belongs to [camara-2025](https://camaraproject.org) (Apache-2.0). This repository does not restate or rename it: `schema/` holds the standard's own objects, each linked to the release it was read from, and `crosswalk/` measures, from each provider's harvested OpenAPI, which operations it implements and what share of the standard's request and response fields it carries.

Measured across 282 providers tagged Telecommunications, Telecom, Mobile Network Operator, Network APIs, CAMARA, 5G, Open Gateway, Communications, Identity Verification, Fraud Prevention in [APIs.io](https://apis.io): **8 implement the standard**; 16 name it somewhere in a spec.

## The standard's APIs

| API | Release | Implementers | Operations |
| --- | --- | ---: | --- |
| number-verification | [r4.2](https://github.com/camaraproject/NumberVerification/tree/r4.2) | 6 | `POST /verify`, `GET /device-phone-number` |
| sim-swap | [r4.3](https://github.com/camaraproject/SimSwap/tree/r4.3) | 7 | `POST /check`, `POST /retrieve-date` |
| location-verification | [r3.2](https://github.com/camaraproject/DeviceLocation/tree/r3.2) | 2 | `POST /verify` |
| location-retrieval | [r3.2](https://github.com/camaraproject/DeviceLocation/tree/r3.2) | 1 | `POST /retrieve` |
| device-reachability-status | [r2.2](https://github.com/camaraproject/DeviceStatus/tree/r2.2) | 1 | `POST /retrieve` |
| device-roaming-status | [r2.2](https://github.com/camaraproject/DeviceStatus/tree/r2.2) | 2 | `POST /retrieve` |
| kyc-match | [r2.2](https://github.com/camaraproject/KnowYourCustomer/tree/r2.2) | 3 | `POST /match` |
| quality-on-demand | [r3.2](https://github.com/camaraproject/QualityOnDemand/tree/r3.2) | 2 | `POST /sessions`, `GET /sessions/{sessionId}` |

## Implementers

Coverage is the best-matching operation's share of the standard's fields, per API.

| Provider | APIs (field coverage) |
| --- | --- |
| [america-movil](https://apis.io/providers/america-movil/) | sim-swap 100% |
| [att](https://apis.io/providers/att/) | number-verification 67%, sim-swap 100% |
| [infobip](https://apis.io/providers/infobip/) | kyc-match 100%, number-verification 100%, sim-swap 100% |
| [kpn](https://apis.io/providers/kpn/) | sim-swap 67% |
| [orange](https://apis.io/providers/orange/) | number-verification 100% |
| [orange-business](https://apis.io/providers/orange-business/) | device-reachability-status 100%, device-roaming-status 100%, kyc-match 100%, location-retrieval 83%, location-verification 86%, number-verification 100%, quality-on-demand 100%, sim-swap 100% |
| [telefonica](https://apis.io/providers/telefonica/) | device-roaming-status 100%, location-verification 86%, number-verification 67%, quality-on-demand 54%, sim-swap 100% |
| [telstra](https://apis.io/providers/telstra/) | kyc-match 98%, number-verification 100%, sim-swap 100% |

The standard's own publishing bodies are listed in the catalog too ([camara-project](https://apis.io/providers/camara-project/), [global-system-for-mobile-communications](https://apis.io/providers/global-system-for-mobile-communications/), [gsma](https://apis.io/providers/gsma/), [open-gateway](https://apis.io/providers/open-gateway/)); they carry the specifications verbatim and are not counted as implementers.

## Findings

- Eight operators and communications platforms implement CAMARA in their own published OpenAPI, out of 282 telecom, identity and fraud providers measured. Number verification (6) and SIM swap (7) lead; location, device status and quality on demand are each implemented by one or two.
- Implementers that publish CAMARA carry its fields intact: the best-matching operation for number verification, SIM swap and KYC match reaches 100% coverage at most of them.

## Decisions

- A reference context publishes the standard's objects under the standard's own names (camelCase), and the commons naming ruleset does not apply to them: renaming a standard's fields would fork it.
- The standard body's own catalog listings (camara-project, gsma, global-system-for-mobile-communications, open-gateway) are listed as publishers and not counted, because they carry the specification verbatim.
- Pinned to the latest release of each CAMARA API repository at measurement time, not to main, which carries work-in-progress versions.

## Licence

Measurements (profile, crosswalks, adopters) are CC BY-NC-SA 4.0; code is Apache 2.0. The standard's objects in `schema/` remain under the standard's own licence (Apache-2.0).
