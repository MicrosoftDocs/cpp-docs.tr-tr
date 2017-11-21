---
title: "Uluslararası duruma getirme stratejileri | Microsoft Docs"
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
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 944ba06bd7b3d81abb2ab431494096f9ade77574
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="internationalization-strategies"></a>Uluslararası Duruma Getirme Stratejileri
Hedef işletim sistemi ve pazarlara bağlı olarak birkaç uluslararası duruma getirme stratejileri vardır:  
  
-   Uygulamanızı Unicode kullanır ve bu nedenle Windows 2000 ve Windows NT, ancak Windows 95 veya Windows 98 çalıştırır.  
  
     Tüm karakterleri, 16 bit uzunluğunda (ANSI karakter programınızın bazı bölümlerinde özel amaçlarla kullanabilirsiniz ancak) ve Unicode özgü işlevsellik kullanın. C çalışma zamanı kitaplığı işlevleri, makroları ve veri türleri için yalnızca Unicode programlama sağlar. MFC tam Unicode etkindir.  
  
-   Uygulamanızın MBCS kullanır ve herhangi bir Win32 platformda çalışabilir.  
  
     MBCS özgü işlevini kullanın. Dizeleri tek baytlık karakterler, çift baytlık karakterler ya da her ikisini de içerebilir. C çalışma zamanı kitaplığı işlevleri, makroları ve veri türleri için sadece MBCS programlama sağlar. MFC tam MBCS etkindir.  
  
-   Uygulamanız için kaynak kodu tam taşınabilirlik için yazılmıştır — simgesiyle yeniden derlenmesi tarafından **_UNICODE** veya sembol **_MBCS** tanımlanan kullanın ya da sürümleri üretebilir. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Uygulamanızı bir açıklandığı gibi eksik Windows 95, Windows 98 ve Windows ME Unicode işlevleri için sarmalayıcı kitaplık kullanır [hem Windows 98 ve Windows 2000 çalıştıran tek bir Unicode Uygulaması Tasarlama](http://go.microsoft.com/fwlink/p/?LinkId=250770). Sarmalayıcı kitaplıklar de ticari olarak kullanılabilir.  
  
     Tümüyle taşınabilir C çalışma zamanı işlevleri, makroları ve veri türlerini kullanın. MFC'nin esnekliği bu stratejileri destekler.  
  
 Bu konularda geri kalanı Unicode veya MBCS olarak yapı tümüyle taşınabilir kod yazmaya odaklanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode ve MBCS](../text/unicode-and-mbcs.md)   
 [Yerel ayarlar ve kod sayfaları](../text/locales-and-code-pages.md)