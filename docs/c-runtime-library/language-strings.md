---
title: Dil Dizeleri
ms.date: 11/04/2016
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
ms.openlocfilehash: 18a94d33f9ca382bb6c7cd77a4f2b33ed800f2c6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438255"
---
# <a name="language-strings"></a>Dil Dizeleri

[Setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) ve [_Create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) işlevleri, Unicode kod sayfasını kullanmayan işletim sistemlerinde Windows nls API 'si tarafından desteklenen dilleri kullanabilir. İşletim sistemi sürümüne göre desteklenen dillerin listesi için bkz. [ek a:](https://msdn.microsoft.com/library/cc233982.aspx) [MS-LCID] Içinde ürün davranışı: Windows dil kodu tanımlayıcısı (LCID) başvurusu. Dil dizesi, desteklenen diller listesinin **dil** ve **Dil etiketi** sütunlarındaki değerlerden herhangi biri olabilir. Kullanılabilir yerel ayar adlarını ve ilgili değerleri gösteren bir kod örneği için bkz. [NLS: ad tabanlı API 'Ler örneği](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-language-strings"></a>Desteklenen ek dil dizeleri

Microsoft C çalışma zamanı kitaplığı uygulamasında da bu dil dizeleri desteklenir:

|Dil dizesi|Eşdeğer yerel ayar adı|
|---------------------|----------------------------|
|İngilizcesi|tr-TR|
|Amerikan İngilizcesi|tr-TR|
|Amerikan-İngilizce|tr-TR|
|ticari|tr-AU|
|Belçika|nl-|
|alı|CA tr|
|CHH|zh-HK|
|kikare dağılımı|zh-SG|
|Çince|zh|
|Çince-Hongkong|zh-HK|
|Çince-Basitleştirilmiş|zh-CN|
|Çince-Singapur|zh-SG|
|Çince-Geleneksel|zh-TW|
|Felemenkçe-Belçika|nl-|
|İngilizce-American|tr-TR|
|İngilizce-Avustralya|tr-AU|
|İngilizce-Belize|En-BZ|
|İngilizce-can|CA tr|
|İngilizce-Karayipler|En-029|
|İngilizce-ire|IE tr|
|İngilizce-Jamaika|En-JM|
|İngilizce-NZ|tr NZ|
|İngilizce-Güney Afrika|En-ZA|
|İngilizce-Trinidad y Tobago|En-TT|
|İngilizce-UK|en-GB|
|İngilizce-ABD|tr-TR|
|İngilizce-ABD|tr-TR|
|Fransızca-Belçika|fr-of|
|Fransızca-Kanada|fr-CA|
|Fransızca-Lüksemburg|fr-LU|
|Fransızca-İsviçre|FR-CH|
|Almanca-Avusturya|de-AT|
|Almanca-Lichtenstein|de LI|
|Almanca-Lüksemburg|de-LU|
|Almanca-İsviçre|de-CH|
|İrlanda Dili-İngilizce|IE tr|
|İtalyanca-İsviçre|It-CH|
|Norveç dili|hayır|
|Norveççe-Bokmal|NB-yok|
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
|Alman|de-CH|
|tr|en-GB|
|ABD|tr-TR|
|ABD|tr-TR|

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Ülke/bölge dizeleri](../c-runtime-library/country-region-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
