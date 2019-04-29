---
title: Dil Dizeleri
ms.date: 11/04/2016
f1_keywords:
- c.strings
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
ms.openlocfilehash: 143f06a0cf22265734d6d77f8fca4efd5ac3031b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62343166"
---
# <a name="language-strings"></a>Dil Dizeleri

[Setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) ve [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) işlevleri Unicode kod sayfası kullanmayın işletim sistemlerinde Windows NLS API desteklenen dilleri kullanabilirsiniz. İşletim sistemi sürümü tarafından desteklenen dillerin bir listesi için bkz. [ek A: Ürün davranışı](https://msdn.microsoft.com/library/cc233982.aspx) [MS-LCID] içinde: Windows dil kodu tanımlayıcı (LCID) başvuru. Dil dizesi değerleri olabilir **dil** ve **dil etiketi** sütunlarının desteklenen dillerin listesi. Kullanılabilen yerel veri adları ve ilgili değerleri numaralandırır kod örneği için bkz: [NLS: Ad tabanlı API'ler örnek](/windows/desktop/intl/nls--name-based-apis-sample).

## <a name="additional-supported-language-strings"></a>Ek desteklenen dil dizeleri

Microsoft C çalışma zamanı kitaplığı uygulaması da bu dil dizeleri destekler:

|Dil dizesi|Eşdeğer yerel ayar adı|
|---------------------|----------------------------|
|American|en-US|
|Amerikan İngilizcesi|en-US|
|Amerikan İngilizcesi|en-US|
|Avustralya|tr-AU|
|Belçika|NL-olabilir|
|Kanada|CA tr|
|CHH|zh-HK|
|Chi|zh-SG|
|Çince|zh|
|chinese-hongkong|zh-HK|
|Çince (Basitleştirilmiş)|zh-CN|
|Çince-Singapur|zh-SG|
|Çince (Geleneksel)|zh-TW|
|Hollanda dili-Belçika|NL-olabilir|
|İngilizce-Amerika|en-US|
|İngilizce-Avustralya|tr-AU|
|İngilizce-belize|tr BZ|
|İngilizce-can|CA tr|
|İngilizce-Karayipler|tr 029|
|İngilizce-Bitir|IE tr|
|İngilizce-Jamaika|JM tr|
|english-nz|tr NZ|
|İngilizce-Güney Afrika|tr-ZA|
|İngilizce-trinidad ve tobago|tr TT|
|İngilizce-Birleşik Krallık|en-GB|
|İngilizce-ABD|en-US|
|İngilizce-ABD|en-US|
|Fransızca-Belçika|FR-olabilir|
|French-Canadian|fr-CA|
|Fransızca-Lüksemburg|FR-LU|
|Fransızca-İsviçre|FR-CH|
|Almanca-Avusturya|de-AT|
|Almanca-lichtenstein|de-LI|
|Almanca-Lüksemburg|de-LU|
|Almanca-İsviçre|de-CH|
|İrlanda dili-İngilizce|IE tr|
|İtalyanca-İsviçre|BT CH|
|Norveç dili|Yok|
|Norveççe bokmal|NB-yok|
|Norveççe nynorsk|nn yok|
|Portekizce-Brezilya|pt-BR|
|İspanyolca-Arjantin|es-AR|
|İspanyolca-Bolivya|ES BO|
|İspanyolca-Şili|ES-CL|
|İspanyolca-Kolombiya|ES-CO|
|İspanyolca-Kosta Rika|es-CR|
|İspanyolca-Dominik Cumhuriyeti|ES yapın|
|İspanyolca-Ekvador|ES-EC|
|İspanyolca-el salvador|es-SV|
|İspanyolca-guatemala|ES-GT|
|İspanyolca-honduras|ES HN|
|İspanyolca-Meksika|es-MX|
|İspanyolca-modern|es-ES|
|İspanyolca-Nikaragua|ES-nı|
|İspanyolca-panama|ES-PA|
|İspanyolca-paraguay|ES-Kopyala|
|İspanyolca-peru|ES PE|
|İspanyolca-Porto Riko|ES-çekme isteği|
|İspanyolca-uruguay|es-UY|
|spanish-venezuela|ES Kaydet|
|İsveççe-Finlandiya|sv-FI|
|İsviçre|de-CH|
|Birleşik Krallık|en-GB|
|ABD|en-US|
|USA|en-US|

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Ülke/bölge dizeleri](../c-runtime-library/country-region-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
