---
title: Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
ms.openlocfilehash: 0b43168ec4331e99dea7e939b097674cc880804e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375763"
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)

Çok bayt karakter kümeleri (MBCSs), Tek bir baytta temsil edilemeyen Japonca ve Çince gibi karakter kümelerini destekleme gereksinimine daha eski bir yaklaşımdır. Yeni geliştirme yapıyorsanız, son kullanıcılar tarafından görülmeyen sistem dizeleri dışında tüm metin dizeleri için Unicode kullanmanız gerekir. MBCS eski bir teknolojidir ve yeni geliştirme için önerilmez.

En yaygın MBCS uygulaması çift bayt karakter kümeleridir (DBCSs). Genel olarak Visual C++ ve özellikle MFC DBCS için tam olarak etkinleştirilmiştir.

Örnekler için MFC kaynak kodu dosyalarına bakın.

Dilleri büyük karakter kümeleri kullanan pazarlarda kullanılan platformlar için Unicode'a en iyi alternatif MBCS'dir. MFC, uluslararası veri türleri ve C çalışma zamanı işlevleri kullanarak MBCS'yi destekler. Aynısını kodunuzda da yapmalısınız.

MBCS altında, karakterler 1 veya 2 bayt olarak kodlanır. 2 bayt karakterde, ilk veya kurşun bayt, hem onun hem de aşağıdaki baytın tek bir karakter olarak yorumlanması gerektiğini bildirir. İlk bayt, kurşun bayt olarak kullanılmak üzere ayrılmış bir dizi koddan gelir. Hangi bayt aralıklarının kurşun bayt olabileceği, kullanılan kod sayfasına bağlıdır. Örneğin, Japonca kod sayfası 932, 0x81 ile 0x9F aralığını kurşun bayt olarak kullanır, ancak Kore kodu sayfası 949 farklı bir aralık kullanır.

MBCS programlamanızda aşağıdakilerin tümlerini göz önünde bulundurun.

OrtamdamBCS karakterleri dosya ve dizin adları gibi dizeleri görünebilir.

### <a name="editing-operations"></a>Düzenleme işlemleri

MBCS uygulamalarındaki düzenleme işlemleri baytlar üzerinde değil, karakterler üzerinde çalışmalıdır. Caret bir karakteri bölmemeli, **Sağ Ok** tuşu bir karakteri sağa hareket ettirmelidir ve böyle devam etmelidir. **Silme** bir karakteri silmek gerekir; **Geri al** yeniden takmalıdır.

### <a name="string-handling"></a>Dize işleme

MBCS kullanan bir uygulamada, dize işleme özel sorunlar oluşturur. Her iki genişlikteki karakterler tek bir dizede karıştırılır; bu nedenle, kurşun bayt olup olmadığından denetlemeyi unutmamalısınız.

### <a name="run-time-library-support"></a>Çalışma zamanı kitaplık desteği

C çalışma zamanı kitaplığı ve MFC tek bayt, MBCS ve Unicode programlamayı destekler. Tek bayt dizeleri çalışma zamanı `str` işlevleri ailesi ile işlenir, MBCS dizeleri `_mbs` karşılık gelen işlevlerle işlenir ve `wcs` Unicode dizeleri karşılık gelen işlevlerle işlenir. MFC sınıfı üye işlev uygulamaları, "MBCS/Unicode taşınabilirliği" `str` olarak açıklandığı gibi, doğru koşullar altında normal işlev ailesine, MBCS işlevlerine veya Unicode işlevlerine eşleyen taşınabilir çalışma zamanı işlevlerini kullanır.

### <a name="mbcsunicode-portability"></a>MBCS/Unicode taşınabilirliği

tchar.h üstbilgi dosyasını kullanarak, aynı kaynaklardan tek bayt, MBCS ve Unicode uygulamaları oluşturabilirsiniz. Tchar.h, *uygun* şekilde , `str`yani `_mbs` `wcs` işlevleri eşleyen _tcs ile önceden belirlenmiş makroları tanımlar. MBCS oluşturmak için sembolü `_MBCS`tanımlayın. Unicode oluşturmak için, `_UNICODE`sembolü tanımlayın. Varsayılan olarak, `_UNICODE` MFC uygulamaları için tanımlanır. Daha fazla bilgi için [tchar.h'deki Genel Metin Eşlemeleri'ne](../text/generic-text-mappings-in-tchar-h.md)bakın.

> [!NOTE]
> Her ikisini `_UNICODE` de `_MBCS`ve .

Mbctype.h ve Mbstring.h üstbilgi dosyaları, bazı durumlarda ihtiyaç duyabileceğiniz MBCS'ye özgü işlevleri ve makroları tanımlar. Örneğin, `_ismbblead` bir dizedeki belirli bir baytın müşteri adayı bayt olup olmadığını söyler.

Uluslararası taşınabilirlik için programınızı [Unicode](../text/support-for-unicode.md) veya multibayt karakter kümeleri (MBCS) ile kodlayın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Programımda MBCS'yi etkinleştirme](../text/international-enabling.md)

- [Programımda hem Unicode'u hem de MBCS'yi etkinleştirme](../text/internationalization-strategies.md)

- [Uluslararası laştırılmış bir program oluşturmak için MBCS'yi kullanın](../text/mbcs-programming-tips.md)

- [MBCS programlamanın özetine bakın](../text/mbcs-programming-tips.md)

- [Bayt genişliği taşınabilirliği için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve Dizeleri](../text/text-and-strings-in-visual-cpp.md)<br/>
[Visual C++'ta MBCS Desteği](../text/mbcs-support-in-visual-cpp.md)
