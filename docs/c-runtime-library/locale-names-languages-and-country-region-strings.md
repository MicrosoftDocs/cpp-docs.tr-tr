---
title: Yerel ayar adları, diller ve ülke bölgesi dizeleri
ms.date: 12/10/2018
helpviewer_keywords:
- country/region strings
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
ms.openlocfilehash: d9baf3622064a7f035d0eb2b096916ae81a3bd50
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443118"
---
# <a name="ucrt-locale-names-languages-and-countryregion-strings"></a>UCRT yerel ayar adları, diller ve ülke/bölge dizeleri

Setlocale 'in *yerel ayar* bağımsız değişkeni, [\_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), [\_\_yerel ayar oluştur](../c-runtime-library/reference/create-locale-wcreate-locale.md)ve [\_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) işlevleri, yerel ayar adları, DILLER, ülke/bölge kodları ve Windows nls API tarafından desteklenen kod sayfaları kullanılarak ayarlanabilir. *Yerel ayar* bağımsız değişkeni aşağıdaki biçimi alır:

> *yerel ayar* :: "*yerel ayar-adı*"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| "*dil*\[ **\_** _ülke bölge_\[ __.__ *kod sayfası*]] "<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| " __.__ *kod sayfası*"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| "C"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| ""<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| NULL

*Locale-Name* formu, bir Short, IETF-standartlaştırılmış dizedir; Örneğin, Ingilizce (Birleşik Devletler) `bs-Cyrl-BA` veya Boşnakça (Kiril, Bosna-Hersek) için `en-US`. Bu formlar tercih edilir. Windows işletim sistemi sürümü tarafından desteklenen yerel ayar adlarının bir listesi için bkz. Ek A 'daki tablonun **Dil etiketi** sütunu. [MS-LCID]: Windows dil kodu tanımlayıcısı (LCID) başvurusu Içindeki [ürün davranışı](https://msdn.microsoft.com/library/cc233982.aspx) . Bu kaynak yerel ayar adlarının desteklenen dilini, betiğini ve bölge bölümlerini listeler. Varsayılan olmayan sıralama düzenlerine sahip desteklenen yerel ayar adları hakkında daha fazla bilgi için [sıralama düzeni tanımlayıcılarında](/windows/win32/Intl/sort-order-identifiers) **yerel ayar adı** sütununa bakın. Windows 10 veya üzeri sürümlerinde, geçerli [bcp-47](https://tools.ietf.org/html/bcp47) dil etiketlerine karşılık gelen yerel ayar adlarına izin verilir. Örneğin, `jp-US` geçerli bir BCP-47 etikettir, ancak yerel ayar işlevselliği için etkin bir şekilde yalnızca `US`.

*Dil*\[_ülke bölgesi_\[ **\_** __.__ *kod sayfası*]] Form, yerel ayarı oluşturmak için bir dil dizesi veya dil dizesi ve ülke veya bölge dizesi kullanıldığında bir kategori için yerel ayar ayarında depolanır. Desteklenen dil dizeleri kümesi, [dil dizeleri](../c-runtime-library/language-strings.md)bölümünde açıklanmış ve desteklenen ülke ve bölge dizelerinin listesi [ülke/bölge dizelerinde](../c-runtime-library/country-region-strings.md)listelenmiştir. Belirtilen dil belirtilen ülke veya bölge ile ilişkili değilse, belirtilen ülkenin veya bölgenin varsayılan dili yerel ayar ayarında saklanır. Bu dizelerin bir yerel ayar adı formundansa bir işletim sistemi güncelleştirmesi tarafından değiştirilmesi daha olası olduğundan, kod içinde gömülü veya depolama için seri hale getirilmiş yerel ayar dizeleri için bu biçim önerilmez.

*Kod sayfası* , yerel AYARıYLA ilişkili ANSI/OEM kod sayfasıdır. Bir yerel ayarı yalnızca dile veya dile ve ülkeye/bölgeye göre belirttiğinizde kod sayfası sizin için belirlenir. Özel değer `.ACP` ülke/bölge için ANSI kod sayfasını belirtir. Özel değer `.OCP` ülke/bölge için OEM kod sayfasını belirtir. Örneğin, yerel ayar olarak `"Greek_Greece.ACP"` belirtirseniz, yerel ayar `Greek_Greece.1253` (Yunanca için ANSI kod sayfası) olarak depolanır ve yerel ayar olarak `"Greek_Greece.OCP"` belirtirseniz, `Greek_Greece.737` olarak depolanır (Yunanca için OEM kod sayfası). Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md). Windows üzerinde desteklenen kod sayfalarının bir listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Yerel ayarı belirtmek için yalnızca kod sayfasını kullanırsanız, kullanıcının varsayılan dili ve [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename) tarafından raporlanan ülke/bölge kullanılır. Örneğin, Ingilizce (Birleşik Devletler) için yapılandırılmış bir kullanıcının yerel ayarı olarak `".1254"` (ANSI Türkçe) belirtirseniz, depolanan yerel ayar `English_United States.1254`. Tutarsız davranışa neden olabileceğinden, bu biçim önerilmez.

`C` *yerel ayar* bağımsız değişkeni değeri, C çevirisi için en az ANSI uyumlu ortamı belirtir. `C` yerel ayarı, her **char** veri türünün 1 bayt ve değeri her zaman 256 ' den küçük olduğunu varsayar. *Yerel ayar* boş bir dizeye işaret ediyorsa, yerel ayar uygulama tanımlı yerel ortamdır.

`LC_ALL` kategorisini kullanarak `setlocale` ve `_wsetlocale` işlevleri için aynı anda tüm yerel ayar kategorilerini belirtebilirsiniz. Kategorilerin tümü aynı yerel ayara ayarlanabilir veya bu biçime sahip bir yerel bağımsız değişken kullanarak her kategoriyi ayrı ayrı ayarlayabilirsiniz:

> *LC-All-belirtici* :: *locale*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| \[**LC_COLLATE =** _locale_]\[ **; LC_CTYPE =** _locale_]\[ **; LC_MONETARY =** _locale_]\[ **; LC_NUMERIC =** _locale_]\[ **; LC_TIME =** _yerel ayar_]

Noktalı virgüllerle ayrılmış şekilde, birden çok kategori türü belirtebilirsiniz. Belirtilmemiş kategori türleri geçerli yerel ayarı kullanır. Örneğin, bu kod parçacığı tüm kategoriler için geçerli yerel ayarı `de-DE`olarak ayarlar ve ardından `LC_MONETARY` Kategoriler `en-GB` ve `LC_TIME` `es-ES`olarak ayarlar:

```C
_wsetlocale(LC_ALL, L"de-DE");
_wsetlocale(LC_ALL, L"LC_MONETARY=en-GB;LC_TIME=es-ES");
```

## <a name="see-also"></a>Ayrıca bkz.

[C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)<br/>
[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[Dil Dizeleri](../c-runtime-library/language-strings.md)<br/>
[Ülke/bölge dizeleri](../c-runtime-library/country-region-strings.md)
