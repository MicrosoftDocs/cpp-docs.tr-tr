---
title: "Unicode desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: b58901f213d5e69eb50ad449a87266736fba0af7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="support-for-unicode"></a>Unicode Desteği
Unicode temsil edilemeyen yalnızca tek baytlık dahil olmak üzere tüm karakter kümelerini desteklemek için bir özelliğidir. Uluslararası pazar için programlama yapıyorsanız ya da Unicode kullanmanızı öneririz veya [birden çok baytlı karakter kümeleri](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS'ler) veya bir anahtarı değiştirerek ya da oluşturabilirsiniz programınızı etkinleştirin.  
  
 Geniş karakter 2-bayt çok dilli karakter kodudur. Teknik simgeleri ve özel yayımlama karakterleri dahil olmak üzere çoğu karakter modern dünyanın her yerinde, bilgisayar kullanılan geniş karakter olarak Unicode belirtimine göre temsil edilebilir. Yalnızca bir geniş karakter temsil edilemeyen karakterler Unicode yedek özelliğini kullanarak bir Unicode çift gösterilebilir. Geniş karakterler kullanarak her geniş karakter 16 bit sabit bir boyuta temsil edildiği için uluslararası karakter kümeleri ile programlama basitleştirir.  
  
 Bir joker karakter dizesi olarak temsil edilen bir **wchar_t** dizi ve işaret ediyor bir `wchar_t*` işaretçi. Herhangi bir ASCII karakter karakterin Harf L ekleyerek geniş karakter olarak gösterilebilir. Örneğin, geniş sonlandırma L '\0' dir (16-bit) **NULL** karakter. Benzer şekilde, herhangi bir ASCII dize sabit değeri bir joker karakter dize sabit değeri ASCII değişmez değeri (L "Hello") L Harfi ekleyerek temsil edilebilir.  
  
 Genellikle, geniş karakterler çok baytlı karakter bellekte daha fazla yer kaplar ancak işlem daha hızlıdır. Ayrıca, yalnızca bir yerel ayar aynı anda birden çok baytlı kodlamada temsil, dünyanın tüm karakter kümeleri ise aynı anda Unicode gösterimi tarafından temsil edilir.  
  
 MFC çerçevesi Unicode boyunca etkindir ve MFC Unicode taşınabilir makroları kullanarak aşağıdaki tabloda gösterildiği gibi etkinleştirmesini gerçekleştirir.  
  
### <a name="portable-data-types-in-mfc"></a>MFC'deki taşınabilir veri türleri  
  
|Olmayan taşınabilir veri türü|Bu makro tarafından değiştirildi|  
|-----------------------------|----------------------------|  
|`char`|_**TCHAR**|  
|**char\***, **LPSTR (Win32 veri türü)**|`LPTSTR`|  
|**const char\*, LPCSTR (Win32 veri türü)**|`LPCTSTR`|  
  
 Sınıf `CString` kullanan **_TCHAR** tabanı olarak ve kolay dönüştürmelerde oluşturucular ve işleçler sağlar. Temel işlem birimi bir 8 bit bayt yerine bir 16 bit karakter olması dışında Windows ANSI karakter kümesini işlemek için kullanılan aynı mantığı kullanarak dize işlemlerinin çoğu Unicode için yazılabilir. Birden çok baytlı karakter kümeleri ile çalışma, aksine, gerekmez (ve gerekmemelidir) iki ayrı bayt değilmiş gibi bir Unicode karakter kabul eder.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [MFC üzerinden Unicode desteği yükleme](../mfc/unicode-in-mfc.md)  
  
-   [Kendi programımı Unicode etkinleştir](../text/international-enabling.md)  
  
-   [Unicode ve MBCS kendi programımı etkinleştir](../text/internationalization-strategies.md)  
  
-   [Unicode uluslararası bir program oluşturmak için kullanın](../text/unicode-programming-summary.md)  
  
-   [Unicode nasıl Unicode'u programımı daha verimli Windows 2000'de yapar dahil olmak üzere, avantajları hakkında bilgi edinin](../text/benefits-of-character-set-portability.md)  
  
-   [Kendi programımı joker karakter bağımsız değişkenler geçirebilirsiniz wmain kullanın](../text/support-for-using-wmain.md)  
  
-   [Unicode Programlama Özeti bakın](../text/unicode-programming-summary.md)  
  
-   [Bayt genişliği taşınabilirliği için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)   
 [Wmain kullanma desteği](../text/support-for-using-wmain.md)