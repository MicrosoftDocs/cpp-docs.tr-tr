---
title: Ülke / bölge dizeleri
ms.date: 11/04/2016
f1_keywords:
- c.strings
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
ms.openlocfilehash: 3a3bbe9d1278cf733bafbeb23efcb0a1ad577228
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463472"
---
# <a name="countryregion-strings"></a>Ülke/Bölge Dizeleri

Ülke ve bölge dizeleri için bir yerel ayar belirtimi oluşturmak için bir dil dizesi ile birleştirilebilir `setlocale`, `_wsetlocale`, `_create_locale`, ve `_wcreate_locale` işlevleri. Çeşitli Windows işletim sistemi sürümleri tarafından desteklenen ülke ve bölge adlarının bir listesi için bkz. **dil**, **konumu**, ve **dil etiketi** sütunları tablosundaki [ek A: Ürün davranışı](https://msdn.microsoft.com/library/cc233982.aspx) [MS-LCID] de: Windows dil kodu tanımlayıcı (LCID) başvuru. Kullanılabilen yerel veri adları ve ilgili değerleri numaralandırır kod örneği için bkz: [NLS: ad tabanlı API'ler örnek](/windows/desktop/intl/nls--name-based-apis-sample).

## <a name="additional-supported-country-and-region-strings"></a>Ek desteklenen ülke ve bölge dizeleri

Microsoft C çalışma zamanı kitaplığı uygulaması da aşağıdaki ek ülke/bölge dizelerini ve kısaltmalarını destekler:

|Ülke/bölge dizesi|Kısaltması|Eşdeğer yerel ayar adı|
|----------------------------|------------------|----------------------------|
|Amerika|USA|en-US|
|Britanya|GBR|en-GB|
|Çin|CHN|zh-CN|
|Çekçe|CZE|cs-CZ|
|İngiltere|GBR|en-GB|
|Büyük Britanya|GBR|en-GB|
|Hollanda|NLD|NL-NL|
|Hong kong|HKG|zh-HK|
|Yeni Zelanda|NZL|tr NZ|
|Nz|NZL|tr NZ|
|çekme isteği Çin|CHN|zh-CN|
|Çin Halk|CHN|zh-CN|
|Porto Riko|PRI|ES-çekme isteği|
|Slovakça|SVK|SK-SK|
|Güney Afrika|ZAF|ZA AF|
|Güney Kore|KOR|ko-KR|
|Güney Afrika|ZAF|ZA AF|
|Güney Kore|KOR|ko-KR|
|Trinidad ve tobago|EŞİTLEMESİNİ|tr TT|
|Birleşik Krallık|GBR|en-GB|
|Birleşik Krallık|GBR|en-GB|
|Birleşik Devletler|USA|en-US|
|ABD|USA|en-US|

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Dil Dizeleri](../c-runtime-library/language-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
