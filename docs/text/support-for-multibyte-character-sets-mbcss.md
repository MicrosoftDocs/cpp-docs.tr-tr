---
title: "Çok baytlı karakter kümeleri (MBCS'ler) için destek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
caps.latest.revision: "11"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c6c7bd1477f62e9c78b5e71dfe3723e804283d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)
Birden çok baytlı karakter kümeleri (MBCS'ler) gibi Japonca ve tek bir bayt ile temsil edilemez Çince karakter kümelerini desteklemek için gereken eski bir yaklaşım kümesidir. Yeni geliştirme yapıyorsanız, belki de son kullanıcılar tarafından görülmez sistem dizeleri dışındaki tüm metin dizelerini Unicode kullanmanız gerekir. MBCS eski bir teknolojidir ve yeni geliştirme projeleri için önerilmez.  
  
 En yaygın MBCS çift bayt karakter kümeleri (DBCSler) uygulamasıdır. Genel Visual C++ ve MFC özellikle DBCS için tam olarak etkinleştirilmedi.  
  
 MFC kaynak kodu dosyaları örnekleri için bkz.  
  
 Dilleri geniş karakter kümeleri kullanan pazarlarda kullanılan platformlar için en iyi Unicode MBCS alternatifidir. MFC MBCS MBCS'yi veri türleri ve C çalışma zamanı işlevleri kullanarak destekler. Aynı kodunuzda yapmanız gerekir.  
  
 MBCS altında karakterler 1 veya 2 bayt olarak kodlanmıştır. 2-bayt karakter, ilk veya baytı, onu ve aşağıdaki bayt bir karakter yorumlanacağını bildirir. İlk bayta kalan kodları ön bayt olarak kullanılmak üzere ayrılmış bir dizi gelir. Hangi bayt aralıklarının ön baytlar olabileceği kod sayfasına göre değişir. Örneğin, Japonca kod sayfası 932 ön bayt olarak 0x81-0x9F aralığını kullanır, ancak farklı bir aralık Kore dili kod sayfası 949 kullanır.  
  
 MBCS programlamanın tüm aşağıdakileri göz önünde bulundurun.  
  
 Ortamında MBCS karakterleri  
 MBCS karakter dizeleri dosya ve dizin adları gibi görünebilir.  
  
 Düzenleme işlemleri  
 Düzenleme işlemleri MBCS uygulamalarında değil bayt karakter üzerinde çalışması gereken. Düzeltme işareti karakteri bölme değil, sağ ok tuşu bir karakter sağa ve benzeri taşımanız gerekir. **Silme** bir karakter; silmeniz gerekir **Geri** yeniden.  
  
 Dize işleme  
 MBCS kullanan bir uygulama içinde dize işleme özel sorunlar doğurur. Her iki genişlikleri karakterlerinden tek bir dize karıştırılır; Bu nedenle, ön baytları denetlemeyi unutmayın.  
  
 Çalışma zamanı kitaplık desteği  
 MFC ve C çalışma zamanı kitaplığı tek baytlı ve MBCS Unicode desteği programlama. Tek baytlı dizeleri ile işlenir `str` çalışma zamanı işlevleri, MBCS dizeleri ailesi, karşılık gelen ile işlenir `_mbs` işlevler ve Unicode dizeleri işlenir karşılık gelen ile *wcs* İşlevler. MFC sınıf üye işlevi uygulamaları kullanın, normal doğru durumlarda eşleme taşınabilir çalışma zamanı işlevleri `str` "MBCS/Unicode taşınabilirliği içinde." açıklandığı gibi ailesi işlevleri, MBCS işlevleri veya Unicode işlevleri  
  
 MBCS/Unicode taşınabilirliği  
 Tchar.h başlık dosyasını kullanarak, tek baytlı ve MBCS Unicode oluşturabileceğiniz aynı kaynaktan uygulamalar. Tchar.h tanımlar önekine sahip makroları *_tcs* , hangi eşlemek için `str`, `_mbs`, veya *wcs* uygun olarak işlev. MBCS oluşturmak için simge tanımlama **_MBCS**. Unicode oluşturmak için simge tanımlama **_UNICODE**. Varsayılan olarak, **_MBCS** MFC uygulamaları için tanımlanır. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
> [!NOTE]
>  Davranış, her ikisi de tanımlarsanız tanımlanmadı **_UNICODE** ve **_MBCS**.  
  
 MBCS özgü işlevler ve bazı durumlarda gereksinim duyabileceğiniz makroları Mbctype.h ve Mbstring.h başlık dosyaları tanımlayın. Örneğin, `_ismbblead` bir dizeyi belirli bir bayt baytı olup söyler.  
  
 Uluslararası taşınabilirlik için programınızla kod [Unicode](../text/support-for-unicode.md) veya birden çok baytlı karakter kümeleri (MBCS'ler).  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Kendi programımı MBCS etkinleştir](../text/international-enabling.md)  
  
-   [Unicode ve MBCS kendi programımı etkinleştir](../text/internationalization-strategies.md)  
  
-   [MBCS uluslararası bir program oluşturmak için kullanın](../text/mbcs-programming-tips.md)  
  
-   [MBCS programlama özetini bakın](../text/mbcs-programming-tips.md)  
  
-   [Bayt genişliği taşınabilirliği için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)   
 [Visual C++'ta MBCS Desteği](../text/mbcs-support-in-visual-cpp.md)