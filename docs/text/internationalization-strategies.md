---
title: "Uluslararası duruma getirme stratejileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ead6470bbbeacd43326f4373877eb991e5899116
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="internationalization-strategies"></a>Uluslararası Duruma Getirme Stratejileri
Hedef işletim sistemi ve pazarlara bağlı olarak birkaç uluslararası duruma getirme stratejileri vardır:  
  
-   Uygulamanız Unicode kullanır.  
  
     Tüm karakterleri, 16 bit uzunluğunda (ANSI karakter programınızın bazı bölümlerinde özel amaçlarla kullanabilirsiniz ancak) ve Unicode özgü işlevsellik kullanın. C çalışma zamanı kitaplığı işlevleri, makroları ve veri türleri için yalnızca Unicode programlama sağlar. MFC tam Unicode etkindir.  
  
-   Uygulamanızın MBCS kullanır ve herhangi bir Win32 platformda çalışabilir.  
  
     MBCS özgü işlevini kullanın. Dizeleri tek baytlık karakterler, çift baytlık karakterler ya da her ikisini de içerebilir. C çalışma zamanı kitaplığı işlevleri, makroları ve veri türleri için sadece MBCS programlama sağlar. MFC tam MBCS etkindir.  
  
-   Uygulamanız için kaynak kodu tam taşınabilirlik için yazılmıştır — simgesiyle yeniden derlenmesi tarafından **_UNICODE** veya sembol **_MBCS** tanımlanan kullanın ya da sürümleri üretebilir. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
     Tümüyle taşınabilir C çalışma zamanı işlevleri, makroları ve veri türlerini kullanın. MFC'nin esnekliği bu stratejileri destekler.  
  
 Bu konularda geri kalanı Unicode veya MBCS olarak yapı tümüyle taşınabilir kod yazmaya odaklanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode ve MBCS](../text/unicode-and-mbcs.md)   
 [Yerel Ayarlar ve Kod Sayfaları](../text/locales-and-code-pages.md)