---
title: "Kitaplık adlandırma kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NAFXCW.LIB [MFC]
- libraries [MFC], static
- coding conventions [MFC], MFC library names
- NAFXCWD.LIB [MFC]
- console applications [MFC], MFC library versions
- naming conventions [MFC], MFC object code libraries
- object code libraries, MFC naming conventions
- object code libraries
- conventions [MFC], MFC library names
- MFC libraries, naming conventions
ms.assetid: 39fe7d93-5a14-4c6a-b16c-bf318fa01278
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fd3a4464a7857a3fecac040be7b9d4f1161b4a37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="library-naming-conventions"></a>Kitaplık Adlandırma Kuralları
MFC nesne kodu kitaplıkları aşağıdaki adlandırma kurallarını kullanın. Kitaplık adlarının biçimi şöyledir:  
  
 *u*AFX*c*W*d*. LIB  
  
 Burada italik olarak gösterilen küçük harfler, anlamları aşağıdaki tabloda gösterilen tanımlayıcıları için yer tutucuları şunlardır:  
  
### <a name="library-naming-conventions"></a>Kitaplık Adlandırma Kuralları  
  
|Belirleyici|Değerleri ve anlamları|  
|---------------|-------------------------|  
|*u*|ANSI (N) ya da Unicode (U)|  
|*c*|Tür bir program oluşturmak için: C = all|  
|*d*|Hata ayıklama veya yayın: D Debug; = Yayın için belirleyici atlayın|  
  
 Hata ayıklama Intel platformuna yönelik Windows ANSI uygulaması oluşturmak için varsayılan değer: NAFXCWD.Lib. Aşağıdaki tabloda listelenen tüm kitaplıkları dahil edilen \atlmfc\lib dizininde önceden oluşturulmuş.  
  
### <a name="static-link-library-naming-conventions"></a>Statik bağlantı kitaplık adlandırma kuralları  
  
|Kitaplığı|Açıklama|  
|-------------|-----------------|  
|NAFXCW.LIB|MFC statik bağlantı kitaplığı, yayın sürümü|  
|NAFXCWD.LIB|MFC statik bağlantı kitaplığı, hata ayıklama sürümü|  
|UAFXCW. LIB|Unicode desteği, yayın sürümü ile MFC statik bağlantı kitaplığı|  
|UAFXCWD. LIB|Unicode desteği, hata ayıklama sürümü ile MFC statik bağlantı kitaplığı|  
  
> [!NOTE]
>  Bir kitaplığı sürüm yapı gerekiyorsa, \atlmfc\src\mfc dizininde Readme.Txt dosyasına bakın. Bu dosya ile NMAKE sağlanan derleme görevleri dosyası kullanmayı açıklar.  
  
 Daha fazla bilgi için bkz: [MFC DLL'leri için adlandırma kurallarını](../build/naming-conventions-for-mfc-dlls.md) ve [MFC kitaplıkları Unicode sürümleri](../mfc/unicode-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC kitaplık sürümleri](../mfc/mfc-library-versions.md)

