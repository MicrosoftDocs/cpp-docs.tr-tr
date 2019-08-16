---
title: Yerel ayar adları, diller ve ülke bölgesi dizeleri
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
ms.openlocfilehash: 512eb589d964da9ef8e87f4193362c739b39b4b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500056"
---
# <a name="ucrt-locale-names-languages-and-countryregion-strings"></a>UCRT yerel ayar adları, diller ve ülke/bölge dizeleri

[Setlocale ,\_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), [ \_locale oluştur\_](../c-runtime-library/reference/create-locale-wcreate-locale.md)ve [wcreate\_locale işlevlerinin yerel ayar bağımsız değişkeni, yerel ayar adları kullanılarak ayarlanabilir. \_](../c-runtime-library/reference/create-locale-wcreate-locale.md) Windows NLS API 'SI tarafından desteklenen diller, ülke/bölge kodları ve kod sayfaları. *Yerel ayar* bağımsız değişkeni aşağıdaki biçimi alır:

> *yerel ayar* :: "*yerel ayar-adı*"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\|"*dil*\[_Ülke Bölgesi_ . **\_** \[ *kod sayfası*]] "<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\|" __.__ *kod sayfası*"<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\|,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\|""<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\|DEĞER

*Locale-Name* formu, bir Short, IETF-standartlaştırılmış dizedir; Örneğin, `en-US` İngilizce (Birleşik Devletler) veya `bs-Cyrl-BA` Boşnakça (Kiril, Bosna-Hersek) için. Bu formlar tercih edilir. Windows işletim sistemi sürümü tarafından desteklenen yerel ayar adlarının listesi için, ek a 'daki [tablonun **Dil etiketi** sütununa bakın: [MS](https://msdn.microsoft.com/library/cc233982.aspx) -LCID] içinde ürün davranışı: Windows dil kodu tanımlayıcısı (LCıD) başvurusu. Bu kaynak yerel ayar adlarının desteklenen dilini, betiğini ve bölge bölümlerini listeler. Varsayılan olmayan sıralama düzenlerine sahip desteklenen yerel ayar adları hakkında daha fazla bilgi için [sıralama düzeni tanımlayıcılarında](/windows/win32/Intl/sort-order-identifiers) **yerel ayar adı** sütununa bakın. Windows 10 veya üzeri sürümlerinde, geçerli [bcp-47](https://tools.ietf.org/html/bcp47) dil etiketlerine karşılık gelen yerel ayar adlarına izin verilir. Örneğin, `jp-US` geçerli bir bcp-47 etikettir, ancak yalnızca `US` yerel ayar işlevselliği için etkin değildir.

_Ülke Bölgesi_\[dili\[ . **\_** *kod sayfası*]] Form, yerel ayarı oluşturmak için bir dil dizesi veya dil dizesi ve ülke veya bölge dizesi kullanıldığında bir kategori için yerel ayar ayarında depolanır. Desteklenen dil dizeleri kümesi, [dil dizeleri](../c-runtime-library/language-strings.md)bölümünde açıklanmış ve desteklenen ülke ve bölge dizelerinin listesi [ülke/bölge dizelerinde](../c-runtime-library/country-region-strings.md)listelenmiştir. Belirtilen dil belirtilen ülke veya bölge ile ilişkili değilse, belirtilen ülkenin veya bölgenin varsayılan dili yerel ayar ayarında saklanır. Bu dizelerin bir yerel ayar adı formundansa bir işletim sistemi güncelleştirmesi tarafından değiştirilmesi daha olası olduğundan, kod içinde gömülü veya depolama için seri hale getirilmiş yerel ayar dizeleri için bu biçim önerilmez.

*Kod sayfası* , yerel AYARıYLA ilişkili ANSI/OEM kod sayfasıdır. Bir yerel ayarı yalnızca dile veya dile ve ülkeye/bölgeye göre belirttiğinizde kod sayfası sizin için belirlenir. Özel değer `.ACP` ülke/bölge için ANSI kod sayfasını belirtir. Özel değer `.OCP` ülke/bölge için OEM kod sayfasını belirtir. Örneğin, yerel ayar olarak belirtirseniz `"Greek_Greece.ACP"` , yerel ayar olarak `Greek_Greece.1253` depolanır (Yunanca için ANSI kod sayfası) ve yerel ayar olarak belirtirseniz `"Greek_Greece.OCP"` , (Yunanca için OEM kod sayfası) olarak `Greek_Greece.737` depolanır. Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md). Windows üzerinde desteklenen kod sayfalarının bir listesi için bkz. [kod sayfası tanımlayıcıları](/windows/win32/Intl/code-page-identifiers).

Yerel ayarı belirtmek için yalnızca kod sayfasını kullanırsanız, kullanıcının varsayılan dili ve [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename) tarafından raporlanan ülke/bölge kullanılır. Örneğin, İngilizce (Birleşik Devletler) `".1254"` için yapılandırılmış bir kullanıcının yerel ayarı olarak (ANSI Türkçe) belirtirseniz, depolanan yerel ayar olur. `English_United States.1254` Tutarsız davranışa neden olabileceğinden, bu biçim önerilmez.

*Yerel ayar* bağımsız değişkeni değeri `C` , C çevirisi için en az ANSI uyumlu ortamı belirtir. Yerel ayar her char veri türünün 1 bayt ve değeri her zaman 256 ' den küçük olduğunu varsayar. `C` *Yerel ayar* boş bir dizeye işaret ediyorsa, yerel ayar uygulama tanımlı yerel ortamdır.

Kategori kullanarak `_wsetlocale` `setlocale` ,veişlevleriiçinaynıandatümyerelayarkategorilerinibelirtebilirsiniz`LC_ALL` . Kategorilerin tümü aynı yerel ayara ayarlanabilir veya bu biçime sahip bir yerel bağımsız değişken kullanarak her kategoriyi ayrı ayrı ayarlayabilirsiniz:

> *LC-All-belirtici* :: *locale*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;\|LC_COLLATE =_locale_] \[ \[ **; LC_CTYPE =** _yerel ayar_]\[ **; LC_MONETARY =** _yerel ayar_]\[ **; LC_NUMERIC =** _yerel ayar_]\[ **; LC_TIME =** _locale_]

Noktalı virgüllerle ayrılmış şekilde, birden çok kategori türü belirtebilirsiniz. Belirtilmemiş kategori türleri geçerli yerel ayarı kullanır. Örneğin, bu `de-DE`kod parçacığı tüm kategoriler için geçerli yerel ayarı ayarlar ve sonra `en-GB` kategorileri `LC_MONETARY` öğesine ve `LC_TIME` `es-ES`öğesine ayarlar:

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
