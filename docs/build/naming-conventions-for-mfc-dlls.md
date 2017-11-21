---
title: "MFC DLL'leri için adlandırma kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC libraries [C++], naming conventions
- naming conventions [C++], MFC DLLs
- MFC DLLs [C++], naming conventions
- libraries [C++], MFC DLL names
- shared DLL versions [C++]
- DLLs [C++], naming conventions
- DLLs [C++], library names
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b78d01405ca74acfa74f898b88d1c9b79625e99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="naming-conventions-for-mfc-dlls"></a>MFC DLL'leri için Adlandırma Kuralları
MFC'de bulunan kitaplıkları ve DLL'ler yapılandırılmış bir adlandırma kuralını izler. Bu, hangi DLL'i veya kitaplığı hangi amaçla kullanılmalı bilmeniz kolaylaştırır.  
  
 İçeri aktarma kitaplıkları uygulamaları ya da bu DLL'leri kullanan MFC uzantı DLL'leri oluşturmak için gereken DLL olarak aynı taban adına sahip ancak .lib dosya adı uzantısına sahiptir.  
  
### <a name="shared-dll-naming-convention"></a>Paylaşılan DLL adlandırma kuralı  
  
|DLL|Açıklama|  
|---------|-----------------|  
|MFCx0.DLL|MFC DLL, ANSI yayın sürümü|  
|Mfcx0u.DLL'i|MFC DLL, Unicode yayın sürümü|  
|MFCx0D.DLL|MFC DLL, ANSI hata ayıklama sürümü|  
|MFCx0UD.DLL|MFC DLL, Unicode hata ayıklama sürümü|  
  
 Bir uygulama veya MFC uzantı DLL'si olup paylaşılan MFC'nin DLL sürümü, için dinamik olarak bağlıyorsanız, ürünle birlikte MFCx0.DLL eklemeniz gerekir. Unicode desteği uygulamanızda gerekiyorsa, bunun yerine Mfcx0u.DLL'i içerir.  
  
 Statik olarak MFC'ye DLL bağlanıyorsanız, statik MFC kitaplıkları biriyle bağlamanız gerekir. Bu sürümleri kurala göre adlandırılır [N &#124; U] [D] AFXCW. LIB. Daha fazla bilgi için bkz: "Statik bağlantı kitaplık adlandırma kuralları" tablosuna [kitaplık adlandırma kuralları](../mfc/library-naming-conventions.md) (MFC).  
  
 Uygulamalarınızla dağıtılabilir Visual C++ DLL'leri listesi için Visual Studio yüklemenizin Redist.txt'e bakın.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Kitaplıklar için adlandırma kuralları](../mfc/library-naming-conventions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'leri](../build/dlls-in-visual-cpp.md)