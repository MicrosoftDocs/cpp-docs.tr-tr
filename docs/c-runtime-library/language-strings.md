---
title: Dil Dizeleri
ms.date: 11/04/2016
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
ms.openlocfilehash: 7713fe3f7cff4b80ce72927fa970e03914f94346
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373610"
---
# <a name="language-strings"></a>Dil Dizeleri

[Setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) ve [_Create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) işlevleri, Unicode kod sayfasını kullanmayan işletim sistemlerinde Windows nls API 'si tarafından desteklenen dilleri kullanabilir. İşletim sistemi sürümüne göre desteklenen dillerin listesi için bkz. [ek a:](https://docs.microsoft.com/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c) \[ MS-LCID 'de ürün davranışı]: Windows dil kodu tanımlayıcısı (LCID) başvurusu. Dil dizesi, desteklenen diller listesinin **dil** ve **Dil etiketi** sütunlarındaki değerlerden herhangi biri olabilir. Kullanılabilir yerel ayar adlarını ve ilgili değerleri gösteren bir kod örneği için bkz. [NLS: ad tabanlı API 'Ler örneği](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-language-strings"></a>Desteklenen ek dil dizeleri

Microsoft C çalışma zamanı kitaplığı uygulamasında da bu dil dizeleri desteklenir:

|Dil dizesi|Eşdeğer yerel ayar adı|
|---------------------|----------------------------|
|İngilizcesi|tr-TR|
|Amerikan İngilizcesi|tr-TR|
|Amerikan-İngilizce|tr-TR|
|ticari|En-AU|
|Belçika|nl-|
|alı|en-CA|
|CHH|zh-HK|
|kikare dağılımı|zh-SG|
|Çince|zh|
|Çince-Hongkong|zh-HK|
|Çince-Basitleştirilmiş|zh-CN|
|Çince-Singapur|zh-SG|
|Çince-Geleneksel|zh-TW|
|Felemenkçe-Belçika|nl-|
|İngilizce-American|tr-TR|
|İngilizce-Avustralya|En-AU|
|İngilizce-Belize|En-BZ|
|İngilizce-can|en-CA|
|İngilizce-Karayipler|En-029|
|İngilizce-ire|en-IE|
|İngilizce-Jamaika|En-JM|
|İngilizce-NZ|En-NZ|
|İngilizce-Güney Afrika|En-ZA|
|İngilizce-Trinidad y Tobago|En-TT|
|İngilizce-UK|en-GB|
|İngilizce-ABD|tr-TR|
|İngilizce-ABD|tr-TR|
|Fransızca-Belçika|fr-of|
|Fransızca-Kanada|fr-CA|
|Fransızca-Lüksemburg|fr-LU|
|Fransızca-İsviçre|fr-CH|
|Almanca-Avusturya|de|
|Almanca-Lichtenstein|de LI|
|Almanca-Lüksemburg|de-LU|
|Almanca-İsviçre|devre dışı|
|İrlanda Dili-İngilizce|en-IE|
|İtalyanca-İsviçre|It-CH|
|Norveç dili|hayır|
|Norveççe-Bokmal|nb-NO|
|Norveççe-Nynorsk|nn-Hayır|
|Portekizce-Brezilya|pt-BR|
|İspanyolca-Arjantin|es-AR|
|İspanyolca-Bolivya|es-BO|
|İspanyolca-Şili|es-CL|
|İspanyolca-Kolombiya|es-CO|
|İspanyolca-Kosta Rika|es-CR|
|İspanyolca-Dominik Cumhuriyeti|es-DO|
|İspanyolca-Ekvador|es-EC|
|İspanyolca-El Salvador|es-ZF|
|İspanyolca-Guatemala|es-GT|
|İspanyolca-Honduras|es-HN|
|İspanyolca-Meksika|es-MX|
|İspanyolca-modern|es-ES|
|İspanyolca-Nikaragua|es-nı|
|İspanyolca-Panama|es-PA|
|İspanyolca-Paraguay|es-Kopyala|
|İspanyolca-Peru|es-PE|
|İspanyolca-Porto Riko|es-PR|
|İspanyolca-Uruguay|es-UY|
|İspanyolca-Venezuela|es-VE|
|İsveççe-Finlandiya|ZF-FI|
|Alman|devre dışı|
|tr|en-GB|
|ABD|tr-TR|
|ABD|tr-TR|

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Ülke/bölge dizeleri](../c-runtime-library/country-region-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
