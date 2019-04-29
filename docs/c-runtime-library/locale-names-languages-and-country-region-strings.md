---
title: Yerel ayar adları, diller ve ülke / bölge dizeleri
ms.date: 12/10/2018
f1_keywords:
- c.strings
helpviewer_keywords:
- country/region strings
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
ms.openlocfilehash: f6df36aafde9a61a1fd590a7f60b3c17131aadbb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342750"
---
# <a name="ucrt-locale-names-languages-and-countryregion-strings"></a>UCRT yerel ayar adları, diller ve ülke/bölge dizeleri

*Yerel* bağımsız değişkeni [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), [ \_oluşturma\_yerel](../c-runtime-library/reference/create-locale-wcreate-locale.md), ve [ \_wcreate\_yerel ayar](../c-runtime-library/reference/create-locale-wcreate-locale.md) işlevleri, yerel ayar adları, diller, ülke/bölge kodları ve Windows NLS API tarafından desteklenen kod sayfaları kullanılarak ayarlanabilir. *Yerel ayar* bağımsız değişkeni aşağıdaki biçimleri alır:

> *yerel ayar* :: "*yerel ayar adı*"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| "*dil*\[**\_**_ülke / bölge_\[__.__ *kod sayfası*]] "<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| "__.__  *kod sayfası*"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| "C"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| ""<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| NULL

*Yerel ayar adı* biçimidir kısa, IETF standartlaştırılmış bir dize; örneğin, `en-US` İngilizce (ABD) veya `bs-Cyrl-BA` Boşnakça (Kiril, Bosna-Hersek). Şu formlar tercih edilir. Windows işletim sistemi sürümü tarafından desteklenen yerel adlarının listesi için bkz. **dil etiketi** tablodaki sütunun [ek A: Ürün davranışı](https://msdn.microsoft.com/library/cc233982.aspx) [MS-LCID] içinde: Windows dil kodu tanımlayıcı (LCID) başvuru. Bu kaynak yerel ayar adlarının desteklenen dilini, betiğini ve bölge bölümlerini listeler. Sıralama düzenlerine bkz varsayılan olmayan sahip desteklenen yerel ayar adları hakkında bilgi için **yerel ayar adı** sütununda [sıralama düzeni tanımlayıcıları](/windows/desktop/Intl/sort-order-identifiers). İçin geçerli karşılık gelen Windows 10 veya sonraki sürümleri, yerel ayar adları altında [BCP-47](https://tools.ietf.org/html/bcp47) dil etiketlerini izin verilir. Örneğin, `jp-US` geçerli bir BCP-47 etikettir ancak yalnızca etkin olduğu `US` yerel ayar işlevselliği için.

*Dil*\[**\_**_ülke / bölge_\[__.__ *kod sayfası*]] form, yerel ayarda saklanır, bir kategori, bir dil dizesi veya dil dizesi ve ülke veya bölge dizesi yerel ayar oluşturmak için kullanılır. Desteklenen dil dizeleri kümesi açıklanan [dil dizeleri](../c-runtime-library/language-strings.md), ve desteklenen ülke ve bölge dizeleri listesi listelenen [Country/Region Strings](../c-runtime-library/country-region-strings.md). Belirtilen dil belirtilen ülke veya bölge ile ilişkili değilse, belirtilen ülke veya bölge için varsayılan dil yerel ayarda saklanır. Bu dizelerin bir yerel ayar adı formundansa bir işletim sistemi güncelleştirmesi tarafından değiştirilmesi daha olası olduğundan, kod içinde gömülü veya depolama için seri hale getirilmiş yerel ayar dizeleri için bu biçim önerilmez.

*Kod sayfası* yerel ayarla ilişkili ANSI/OEM kod sayfasıdır. Bir yerel ayarı yalnızca dile veya dile ve ülkeye/bölgeye göre belirttiğinizde kod sayfası sizin için belirlenir. Özel değeri `.ACP` ülke/bölge için ANSI kod sayfasını belirtir. Özel değeri `.OCP` ülke/bölge için OEM kod sayfasını belirtir. Örneğin, belirtirseniz `"Greek_Greece.ACP"` yerel ayar olarak, yerel olarak depolanan `Greek_Greece.1253` (ANSI kod sayfası Yunanca için), ve belirtirseniz `"Greek_Greece.OCP"` olarak depolanan yerel ayar `Greek_Greece.737` (Yunanca için OEM kod sayfası). Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md). Windows üzerinde desteklenen kod sayfalarının listesi için bkz. [kod sayfası tanımlayıcıları](/windows/desktop/Intl/code-page-identifiers).

Yerel ayar, kullanıcının varsayılan dil ve ülke/bölge tarafından raporlandığı şekilde belirlemek için yalnızca kod sayfası kullanırsanız [GetUserDefaultLocaleName](/windows/desktop/api/winnls/nf-winnls-getuserdefaultlocalename) kullanılır. Örneğin, belirtirseniz `".1254"` (ANSI Türkçe) İngilizce (ABD) için yapılandırılmış bir kullanıcı için yerel depolanan yerel ayar olan `English_United States.1254`. Tutarsız davranışa neden olabileceğinden, bu biçim önerilmez.

A *yerel* bağımsız değişken değerini `C` C çeviri için en az ANSI uyumlu ortamı belirtir. `C` Yerel varsayar, her **char** veri türünün 1 bayt ve değerinin her zaman 256'dan az olduğu. Varsa *yerel ayar* noktasıdır boş bir dize, yerel ayar uygulama tarafından tanımlanan doğal ortamdır.

İçin aynı anda yerel ayar kategorilerinin tümünü belirtebilirsiniz `setlocale` ve `_wsetlocale` işlevleri kullanarak `LC_ALL` kategorisi. Kategorilerin tümü aynı yerel ayara ayarlanabilir veya bu biçime sahip bir yerel bağımsız değişken kullanarak her kategoriyi ayrı ayrı ayarlayabilirsiniz:

> *LC tüm belirticisi* :: *yerel ayar*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\| \[**LC_COLLATE =**_yerel_]\[**; LC_CTYPE =**_yerel_]\[**; LC_MONETARY =**_yerel_]\[**; Lc_numerıc =**_yerel_]\[**; Lc_tıme =**_yerel ayar_]

Noktalı virgüllerle ayrılmış şekilde, birden çok kategori türü belirtebilirsiniz. Belirtilmemiş kategori türleri geçerli yerel ayarı kullanır. Örneğin, bu kod parçacığı tüm kategorilerin geçerli yerel ayarını ayarlar `de-DE`ve ardından ayarlar `LC_MONETARY` için `en-GB` ve `LC_TIME` için `es-ES`:

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
