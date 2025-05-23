# Client-Locale

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"project"` |

## Wert des Aufzählungstyps

- `"af"`
- `"af-ZA"`
- `"ar"`
- `"ar-AE"`
- `"ar-BH"`
- `"ar-DZ"`
- `"ar-EG"`
- `"ar-IQ"`
- `"ar-JO"`
- `"ar-KW"`
- `"ar-LB"`
- `"ar-LY"`
- `"ar-MA"`
- `"ar-OM"`
- `"ar-QA"`
- `"ar-SA"`
- `"ar-SY"`
- `"ar-TN"`
- `"ar-YE"`
- `"az"`
- `"az-AZ"`
- `"be"`
- `"be-BY"`
- `"bg"`
- `"bg-BG"`
- `"bs-BA"`
- `"ca"`
- `"ca-ES"`
- `"cs"`
- `"cs-CZ"`
- `"cy"`
- `"cy-GB"`
- `"da"`
- `"da-DK"`
- `"de"`
- `"de-AT"`
- `"de-CH"`
- `"de-DE"`
- `"de-LI"`
- `"de-LU"`
- `"dv"`
- `"dv-MV"`
- `"el"`
- `"el-GR"`
- `"en"`
- `"en-AU"`
- `"en-BZ"`
- `"en-CA"`
- `"en-CB"`
- `"en-GB"`
- `"en-IE"`
- `"en-JM"`
- `"en-NZ"`
- `"en-PH"`
- `"en-TT"`
- `"en-US"`
- `"en-ZA"`
- `"en-ZW"`
- `"eo"`
- `"es"`
- `"es-AR"`
- `"es-BO"`
- `"es-CL"`
- `"es-CO"`
- `"es-CR"`
- `"es-DO"`
- `"es-EC"`
- `"es-ES"`
- `"es-GT"`
- `"es-HN"`
- `"es-MX"`
- `"es-NI"`
- `"es-PA"`
- `"es-PE"`
- `"es-PR"`
- `"es-PY"`
- `"es-SV"`
- `"es-UY"`
- `"es-VE"`
- `"et"`
- `"et-EE"`
- `"eu"`
- `"eu-ES"`
- `"fa"`
- `"fa-IR"`
- `"fi"`
- `"fi-FI"`
- `"fo"`
- `"fo-FO"`
- `"fr"`
- `"fr-BE"`
- `"fr-CA"`
- `"fr-CH"`
- `"fr-FR"`
- `"fr-LU"`
- `"fr-MC"`
- `"ga-IE"`
- `"gl"`
- `"gl-ES"`
- `"gu"`
- `"gu-IN"`
- `"he"`
- `"he-IL"`
- `"hi"`
- `"hi-IN"`
- `"hr"`
- `"hr-BA"`
- `"hr-HR"`
- `"hu"`
- `"hu-HU"`
- `"hy"`
- `"hy-AM"`
- `"id"`
- `"id-ID"`
- `"is"`
- `"is-IS"`
- `"it"`
- `"it-CH"`
- `"it-IT"`
- `"ja"`
- `"ja-JP"`
- `"ka"`
- `"ka-GE"`
- `"kk"`
- `"kk-KZ"`
- `"kn"`
- `"kn-IN"`
- `"ko"`
- `"ko-KR"`
- `"kok"`
- `"kok-IN"`
- `"ky"`
- `"ky-KG"`
- `"lt"`
- `"lt-LT"`
- `"lv"`
- `"lv-LV"`
- `"mi"`
- `"mi-NZ"`
- `"mk"`
- `"mk-MK"`
- `"mn"`
- `"mn-MN"`
- `"mr"`
- `"mr-IN"`
- `"ms"`
- `"ms-BN"`
- `"ms-MY"`
- `"mt"`
- `"mt-MT"`
- `"nb"`
- `"nb-NO"`
- `"nl"`
- `"nl-BE"`
- `"nl-NL"`
- `"nn-NO"`
- `"ns"`
- `"ns-ZA"`
- `"pa"`
- `"pa-IN"`
- `"pl"`
- `"pl-PL"`
- `"ps"`
- `"ps-AR"`
- `"pt"`
- `"pt-BR"`
- `"pt-PT"`
- `"qu"`
- `"qu-BO"`
- `"qu-EC"`
- `"qu-PE"`
- `"ro"`
- `"ro-RO"`
- `"ru"`
- `"ru-RU"`
- `"sa"`
- `"sa-IN"`
- `"se"`
- `"se-FI"`
- `"se-NO"`
- `"se-SE"`
- `"sk"`
- `"sk-SK"`
- `"sl"`
- `"sl-SI"`
- `"so-SO"`
- `"sq"`
- `"sq-AL"`
- `"sr-BA"`
- `"sr-SP"`
- `"sv"`
- `"sv-FI"`
- `"sv-SE"`
- `"sw"`
- `"sw-KE"`
- `"syr"`
- `"syr-SY"`
- `"ta"`
- `"ta-IN"`
- `"te"`
- `"te-IN"`
- `"th"`
- `"th-TH"`
- `"tl"`
- `"tl-PH"`
- `"tn"`
- `"tn-ZA"`
- `"tr"`
- `"tr-TR"`
- `"tt"`
- `"tt-RU"`
- `"ts"`
- `"uk"`
- `"uk-UA"`
- `"ur"`
- `"ur-PK"`
- `"uz"`
- `"uz-UZ"`
- `"vi"`
- `"vi-VN"`
- `"xh"`
- `"xh-ZA"`
- `"zh"`
- `"zh-CN"`
- `"zh-HK"`
- `"zh-MO"`
- `"zh-SG"`
- `"zh-TW"`
- `"zu"`
- `"zu-ZA"`
- `"client"`
- `"project"`

## JSON-Schema

```json
{
    "oneOf": [
        {
            "$ref": "tchmi:general#/definitions/Locale"
        },
        {
            "default": "project",
            "description": "descUserLocale",
            "enum": [
                "client",
                "project"
            ],
            "type": "string"
        }
    ]
}
```
