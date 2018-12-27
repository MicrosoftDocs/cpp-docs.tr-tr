---
title: Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)
ms.date: 11/04/2016
f1_keywords:
- _mbcs
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
ms.openlocfilehash: 9f309f6d7147b37691564d3d72c151da90055c6a
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627351"
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)

Çok baytlı karakter kümeleri (MBCSler), Japonca ve Çince tek bir bayt ile gösterilemez gibi karakter kümesi desteklemek için gereken eski bir yaklaşım olan. Yeni geliştirme yapıyorsanız, belki de son kullanıcılar tarafından görülmez sistem dizeleri dışındaki tüm metin dizeleri Unicode kullanmanız gerekir. MBCS, eski bir teknolojidir ve yeni geliştirme projeleri için önerilmez.

En yaygın MBCS çift baytlı karakter kümeleri (DBCSler) uygulamasıdır. Genel Visual C++ ve MFC özellikle DBCS için tam olarak etkinleştirilir.

MFC kaynak kodu dosyaları örnekleri için bkz.

Geniş karakter kümeleri dilleri kullanan pazarlarda kullanılan platformları için en iyi Unicode MBCS alternatiftir. MFC MBCS MBCS'yi veri türleri ve C çalışma zamanı işlevleri kullanarak destekler. Aynı kodunuzda yapmanız gerekir.

MBCS altında 1 veya 2 bayt karakter kodlanır. 2-bayt karakter, first veya baytı, onu ve sonraki bayt bir karakter yorumlanması için bildirir. Ön bayt olarak kullanılmak üzere ayrılmış kodlarının bir aralıktan ilk baytı gelir. Hangi bayt aralığı ön bayt olabilir kod sayfasına bağlıdır. Örneğin, Japonca kod sayfası 932'de ön bayt 0x81-0x9F aralığını kullanır, ancak farklı bir aralık Korece kod sayfası 949 kullanır.

MBCS programlamanın tüm aşağıdakileri göz önünde bulundurun.

MBCS karakter ortam MBCS karakter Dizelerdeki dosya ve dizin adları gibi görünebilir.

### <a name="editing-operations"></a>Düzenleme işlemleri

Düzenleme işlemleri MBCS uygulamalarındaki karakter, bayt sayısını değil çalışması. Giriş işaretini bir karakter bölmeniz gerekir değil **sağ ok** anahtar bir karakter sağa ve benzeri taşıyın. **Silme** bir karakter; silmeniz gerekir **Geri** yeniden.

### <a name="string-handling"></a>Dize işleme

MBCS kullanan bir uygulamada, dize işleme özel sorunlar doğurur. Her iki genişlikleri karakteri tek bir dizede karıştırılır; Bu nedenle ön baytlar için denetlenecek unutmamanız gerekir.

### <a name="run-time-library-support"></a>Çalışma zamanı kitaplık desteği

MFC ve C çalışma zamanı kitaplığı tek baytlık MBCS ve Unicode desteği programlama. Tek baytlı dizeleri ile işlenir `str` çalışma zamanı işlevleri, MBCS dizeleri ailesi, karşılık gelen ile işlenir `_mbs` işlevleri ve Unicode dizeleri işlenir uygun `wcs` işlevleri. MFC sınıf üyesi işlevi uygulamaları kullanın, doğru koşullarda normal harita taşınabilir çalışma zamanı işlevleri `str` "İçinde MBCS/Unicode taşınabilirlik." açıklandığı ailesi işlevleri, MBCS işlevleri veya Unicode işlevleri

### <a name="mbcsunicode-portability"></a>MBCS/Unicode taşınabilirlik

Tchar.h üstbilgi dosyasını kullanarak, tek baytlı MBCS ve Unicode oluşturabileceğinizi aynı kaynaklardan gelen uygulamaları. Tchar.h ön ekine sahip makroları tanımlar *_tcs* , eşleme için `str`, `_mbs`, veya `wcs` İşlevler, uygun şekilde. MBCS oluşturmak için sembolünü tanımlayın `_MBCS`. Unicode oluşturmak için sembolünü tanımlayın `_UNICODE`. Varsayılan olarak, `_UNICODE` MFC uygulamaları için tanımlanır. Daha fazla bilgi için [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).

> [!NOTE]
>  Her ikisi de tanımlarsanız davranışı tanımsız `_UNICODE` ve `_MBCS`.

Mbctype.h ve Mbstring.h üst bilgi dosyaları, MBCS özel işlevler ve bazı durumlarda ihtiyacınız olabilecek makroları tanımlar. Örneğin, `_ismbblead` bir dizede belirli bir bayt bir ön baytı olup söyler.

Uluslararası taşınabilirlik için birlikte kodlayın [Unicode](../text/support-for-unicode.md) veya çok baytlı karakter kümeleri (MBCSler).

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Kendi programımı içinde MBCS etkinleştir](../text/international-enabling.md)

- [Kendi programımı içinde Unicode ve MBCS etkinleştir](../text/internationalization-strategies.md)

- [MBCS uluslararası bir program oluşturmak için kullanın](../text/mbcs-programming-tips.md)

- [MBCS programlama özetini bakın](../text/mbcs-programming-tips.md)

- [Bayt genişlikli taşınabilirlik için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Metin ve Dizeler](../text/text-and-strings-in-visual-cpp.md)<br/>
[Visual C++'ta MBCS Desteği](../text/mbcs-support-in-visual-cpp.md)
