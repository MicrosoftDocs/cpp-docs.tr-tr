---
title: Country-Region dizeleri
description: 'Daha fazla bilgi edinin: ülke/bölge dizeleri'
ms.date: 1/29/2020
helpviewer_keywords:
- country/region strings
ms.openlocfilehash: 34494eb2bcace615e72127ab1735101809e8ade5
ms.sourcegitcommit: beac3ddf1a20de5e836569ae07407d5f3703f536
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2021
ms.locfileid: "99224443"
---
# <a name="countryregion-strings"></a>Ülke/Bölge Dizeleri

Ülke ve bölge dizeleri,,, `setlocale` `_wsetlocale` `_create_locale` ve işlevleri için bir yerel ayar belirtimi oluşturmak üzere bir dil dizesiyle birleştirilebilir `_wcreate_locale` . 

Çeşitli Windows işletim sistemi sürümleri tarafından desteklenen ülke ve bölge adları listeleri için, ek A 'daki tablonun **dil**, **konum** ve **Dil etiketi** sütunlarına bakın: MS-LCID Için [ürün davranışı](/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c) \[ ]: Windows dil kodu tanımlayıcısı (LCID) başvurusu. Kullanılabilir yerel ayar adlarını ve ilgili değerleri gösteren bir kod örneği için bkz. [NLS: ad tabanlı API 'Ler örneği](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-country-and-region-strings"></a>Desteklenen ek ülke ve bölge dizeleri

Microsoft C çalışma zamanı kitaplığı uygulamasında aşağıdaki ek ülke/bölge dizeleri ve kısaltmalar de desteklenir:

|Ülke/bölge dizesi|Kısaltma|Eşdeğer yerel ayar adı|
|----------------------------|------------------|----------------------------|
|`america`|`USA`|`en-US`|
|`britain`|`GBR`|`en-GB`|
|`china`|`CHN`|`zh-CN`|
|`czech`|`CZE`|`cs-CZ`|
|`england`|`GBR`|`en-GB`|
|`great britain`|`GBR`|`en-GB`|
|`holland`|`NLD`|`nl-NL`|
|`hong-kong`|`HKG`|`zh-HK`|
|`new-zealand`|`NZL`|`en-NZ`|
|`nz`|`NZL`|`en-NZ`|
|`pr china`|`CHN`|`zh-CN`|
|`pr-china`|`CHN`|`zh-CN`|
|`puerto-rico`|`PRI`|`es-PR`|
|`slovak`|`SVK`|`sk-SK`|
|`south africa`|`ZAF`|`af-ZA`|
|`south korea`|`KOR`|`ko-KR`|
|`south-africa`|`ZAF`|`af-ZA`|
|`south-korea`|`KOR`|`ko-KR`|
|`trinidad & tobago`|`TTO`|`en-TT`|
|`uk`|`GBR`|`en-GB`|
|`united-kingdom`|`GBR`|`en-GB`|
|`united-states`|`USA`|`en-US`|
|`us`|`USA`|`en-US`|

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Dil dizeleri](../c-runtime-library/language-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
