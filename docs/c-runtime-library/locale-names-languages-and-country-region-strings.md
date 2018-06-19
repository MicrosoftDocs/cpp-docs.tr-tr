---
title: Yerel ayar adları, diller ve ülke bölge dizeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeaeb21dfabac173b639fe4b3e1518b276c629a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391821"
---
# <a name="locale-names-languages-and-countryregion-strings"></a>Yerel Ayar Adları, Diller ve Ülke/Bölge Dizeleri
*Yerel ayar* bağımsız değişkeni `setlocale` ve `_create_locale` işlevleri, yerel ayar adları, diller, ülke/bölge kodları ve Windows NLS API'si tarafından desteklenen kod sayfaları kullanılarak ayarlanabilir. *Yerel* bağımsız değişkeni aşağıdaki formu alır:  
  
> *yerel ayar* :: "*locale_name*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "*dil*\[\_*Ülke*]\[. *code_page*]] "  
&nbsp;&nbsp;&nbsp;&nbsp;| ". *code_page*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "C"  
&nbsp;&nbsp;&nbsp;&nbsp;| ""  
&nbsp;&nbsp;&nbsp;&nbsp;| NULL  
  
 Yerel ayar adı formunu tercih edilir; Örneğin, `en-US` İngilizce (ABD) için veya `bs-Cyrl-BA` Bosna Dili (Kiril, Bosna Hersek) için. Yerel ayar adları kümesi açıklanan [yerel ayar adları](http://msdn.microsoft.com/library/windows/desktop/dd373814.aspx). Windows işletim sistemi sürümü tarafından desteklenen yerel ayar adları listesi için bkz: **kültür adı** sütunu [Ulusal dil desteği (NLS) API Başvurusu](https://www.microsoft.com/resources/msdn/goglobal/default.mspx). Bu kaynak yerel ayar adlarının desteklenen dilini, betiğini ve bölge bölümlerini listeler. Siparişleri sıralamak için bkz: varsayılan olmayan sahip desteklenen yerel ayar adları hakkında bilgi için **yerel ayar adı** sütununda [sıralama sipariş tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/dd374060.aspx). Windows işletim sistemi sürümüne göre dil ve konum desteği hakkında ek bilgi için bkz: [ek A: Ürün davranışı](http://msdn.microsoft.com/goglobal/bb896001.aspx) [MS-LCID] içindeki: Windows dil kodu tanımlayıcısı (LCID) başvurusu. Windows 10 veya sonraki sürümlerinde, geçerli BCP 47 dil etiketleri karşılık gelen yerel adlarına izin verilir. Örneğin, `jp-US` geçerli bir BCP 47 etiket, ancak yalnızca etkili bir şekilde dir `US` yerel işlevselliği için.  
  
 *Dil*[*_country_region*[. *code_page*]] form, yerel ayar depolanır, yerel ayar oluşturmak için bir kategori dil dize veya dil dize ve ülke/bölge dize olduğunda kullanılır. Desteklenen dil dizeler kümesi açıklanan [dil dizeleri](../c-runtime-library/language-strings.md), ve desteklenen ülke/bölge dizeleri listesini listelenen [ülke/bölge dizeleri](../c-runtime-library/country-region-strings.md). Belirtilen dil belirtilen ülke/bölge ile ilişkili değilse, belirtilen ülke/bölge için varsayılan dil yerel ayarda saklanır. Bu dizelerin bir yerel ayar adı formundansa bir işletim sistemi güncelleştirmesi tarafından değiştirilmesi daha olası olduğundan, kod içinde gömülü veya depolama için seri hale getirilmiş yerel ayar dizeleri için bu biçim önerilmez.  
  
 Kod sayfası, yerel ayarla ilişkili ANSI/OEM kod sayfasıdır. Bir yerel ayarı yalnızca dile veya dile ve ülkeye/bölgeye göre belirttiğinizde kod sayfası sizin için belirlenir. Özel değerini `.ACP` ülke/bölge için ANSI kod sayfasını belirtir. Özel değerini `.OCP` ülke/bölge için OEM kod sayfasını belirtir. Örneğin belirtirseniz `"Greek_Greece.ACP"` yerel yerel olarak depolanan `Greek_Greece.1253` (ANSI kod sayfası için Yunanca), ve belirtirseniz `"Greek_Greece.OCP"` olarak depolanan yerel `Greek_Greece.737` (OEM kod sayfası Yunanca için). Kod sayfaları hakkında daha fazla bilgi için bkz: [kod sayfaları](../c-runtime-library/code-pages.md). Desteklenen kod sayfaları Windows'da bir listesi için bkz: [kod sayfası tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/dd317756.aspx).  
  
 Yerel ayarı belirlemek için yalnızca kod sayfası kullanırsanız, sistem varsayılan dili ve ülkesi/bölgesi kullanılır. Örneğin, belirtirseniz `".1254"` (ANSI Türkçe) İngilizce (ABD) için yapılandırılmış bir sistemde yerel depolanan yerel olan `English_United States.1254`. Tutarsız davranışa neden olabileceğinden, bu biçim önerilmez.  
  
A *yerel ayar* bağımsız değişken değeri `C` C çeviri en az ANSI uyumlu ortamını belirtir. `C` Yerel ayar varsayar, her `char` veri türü 1 bayt ve değeri her zaman 256'dan az olduğu. Varsa *yerel* yerel boş bir dize noktalarına uygulama tanımlı yerel ortam olduğu.  
  
Tüm yerel ayar kategorileri için aynı anda belirtebilirsiniz `setlocale` ve `_wsetlocale` kullanarak işlevleri `LC_ALL` kategorisi. Kategorilerin tümü aynı yerel ayara ayarlanabilir veya bu biçime sahip bir yerel bağımsız değişken kullanarak her kategoriyi ayrı ayrı ayarlayabilirsiniz:  
  
> LC_ALL_specifier:: yerel ayar  
&nbsp;&nbsp;&nbsp;&nbsp;| [LC_COLLATE yerel ayar =] [; LC_CTYPE yerel ayar =] [; LC_MONETARY yerel ayar =] [; Lc_numerıc yerel ayar =] [; Lc_tıme yerel ayar =]  
  
Noktalı virgüllerle ayrılmış şekilde, birden çok kategori türü belirtebilirsiniz. Belirtilmemiş kategori türleri geçerli yerel ayarı kullanır. Örneğin, bu kod parçacığını tüm kategorileri geçerli yerel ayarlar `de-DE`ve ardından kategorileri ayarlar `LC_MONETARY` için `en-GB` ve `LC_TIME` için `es-ES`:  
  
```C  
_wsetlocale(LC_ALL, L"de-DE");  
_wsetlocale(LC_ALL, L"LC_MONETARY=en-GB;LC_TIME=es-ES");  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md)   
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [Dil dizeleri](../c-runtime-library/language-strings.md)   
 [Ülke/bölge dizeleri](../c-runtime-library/country-region-strings.md)