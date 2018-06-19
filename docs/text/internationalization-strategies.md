---
title: Uluslararası duruma getirme stratejileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20e4d7b067daedcbc5ce065c096e561dbf932ac1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856602"
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