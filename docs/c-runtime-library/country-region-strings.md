---
title: Ülke bölgesi dizeleri
ms.date: 11/04/2016
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
ms.openlocfilehash: 8556e005618a1b69c47498a07e218284dcb1164f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443437"
---
# <a name="countryregion-strings"></a>Ülke/Bölge Dizeleri

Ülke ve bölge dizeleri, `setlocale`, `_wsetlocale`, `_create_locale`ve `_wcreate_locale` işlevleri için bir yerel ayar belirtimi oluşturmak üzere bir dil dizesiyle birleştirilebilir. Çeşitli Windows işletim sistemi sürümleri tarafından desteklenen ülke ve bölge adları listeleri için, ek A 'daki tablonun **dil**, **konum**ve **dil etıketı** SÜTUNLARıNA bakın: [MS-LCID]: Windows dil kodu tanımlayıcısı (LCID) başvurusu içindeki [ürün davranışı](https://msdn.microsoft.com/library/cc233982.aspx) . Kullanılabilir yerel ayar adlarını ve ilgili değerleri gösteren bir kod örneği için bkz. [NLS: ad tabanlı API 'Ler örneği](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-country-and-region-strings"></a>Desteklenen ek ülke ve bölge dizeleri

Microsoft C çalışma zamanı kitaplığı uygulamasında aşağıdaki ek ülke/bölge dizeleri ve kısaltmalar de desteklenir:

|Ülke/bölge dizesi|Kısaltma|Eşdeğer yerel ayar adı|
|----------------------------|------------------|----------------------------|
|Amerika|ABD|tr-TR|
|Britanya|GBR|en-GB|
|arasında|CHN|zh-CN|
|Çekçe|CZE|cs-CZ|
|İngiltere|GBR|en-GB|
|Büyük Britanya|GBR|en-GB|
|Holland|NLD|NL-NL|
|Hong-Kong|HKG|zh-HK|
|Yeni-Zelanda|NZL|tr NZ|
|NZ|NZL|tr NZ|
|PR Çin|CHN|zh-CN|
|PR-Çin|CHN|zh-CN|
|Porto-Riko|BIRINCIL|es-PR|
|Slovakça|SVK|SK-SK|
|Güney Afrika|ZAF|AF-ZA|
|Güney Kore|KOR|ko-KR|
|Güney Afrika|ZAF|AF-ZA|
|Güney-Kore|KOR|ko-KR|
|Trinidad & Tobago|EŞITLEMESINI|En-TT|
|tr|GBR|en-GB|
|Birleşik Krallık|GBR|en-GB|
|Amerika Birleşik Devletleri|ABD|tr-TR|
|ABD|ABD|tr-TR|

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Dil Dizeleri](../c-runtime-library/language-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
