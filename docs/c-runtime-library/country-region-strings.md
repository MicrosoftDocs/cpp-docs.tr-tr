---
description: 'Daha fazla bilgi edinin: ülke/bölge dizeleri'
title: Country-Region dizeleri
ms.date: 11/04/2016
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
ms.openlocfilehash: d865c3a6a8f505eea7878df379db30224511d51c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195703"
---
# <a name="countryregion-strings"></a>Ülke/Bölge Dizeleri

Ülke ve bölge dizeleri,,, `setlocale` `_wsetlocale` `_create_locale` ve işlevleri için bir yerel ayar belirtimi oluşturmak üzere bir dil dizesiyle birleştirilebilir `_wcreate_locale` . Çeşitli Windows işletim sistemi sürümleri tarafından desteklenen ülke ve bölge adları listeleri için, ek A 'daki tablonun **dil**, **konum** ve **Dil etiketi** sütunlarına bakın: MS-LCID Için [ürün davranışı](/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c) \[ ]: Windows dil kodu tanımlayıcısı (LCID) başvurusu. Kullanılabilir yerel ayar adlarını ve ilgili değerleri gösteren bir kod örneği için bkz. [NLS: ad tabanlı API 'Ler örneği](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-country-and-region-strings"></a>Desteklenen ek ülke ve bölge dizeleri

Microsoft C çalışma zamanı kitaplığı uygulamasında aşağıdaki ek ülke/bölge dizeleri ve kısaltmalar de desteklenir:

|Ülke/bölge dizesi|Kısaltma|Eşdeğer yerel ayar adı|
|----------------------------|------------------|----------------------------|
|Amerika|USA|en-US|
|Britanya|GBR|en-GB|
|arasında|CHN|zh-CN|
|Çekçe|CZE|cs-CZ|
|İngiltere|GBR|en-GB|
|Büyük Britanya|GBR|en-GB|
|Holland|NLD|nl-NL|
|Hong-Kong|HKG|zh-HK|
|Yeni-Zelanda|NZL|En-NZ|
|NZ|NZL|En-NZ|
|PR Çin|CHN|zh-CN|
|PR-Çin|CHN|zh-CN|
|Porto-Riko|BIRINCIL|es-PR|
|Slovakça|SVK|sk-SK|
|Güney Afrika|ZAF|AF-ZA|
|Güney Kore|KOR|ko-KR|
|Güney Afrika|ZAF|AF-ZA|
|Güney-Kore|KOR|ko-KR|
|Trinidad & Tobago|EŞITLEMESINI|En-TT|
|tr|GBR|en-GB|
|Birleşik Krallık|GBR|en-GB|
|Amerika Birleşik Devletleri|USA|en-US|
|ABD|USA|en-US|

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Dil dizeleri](../c-runtime-library/language-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
