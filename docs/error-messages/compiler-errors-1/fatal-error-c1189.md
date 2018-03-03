---
title: "Önemli hata C1189 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2330d49f817012fc2e0381a0991f709ada74ea32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1189"></a>Önemli hata C1189
\#Hata: kullanıcı tarafından sağlanan hata iletisi  
  
 C1189 tarafından oluşturulur `#error` yönergesi. Yönergesi kodları Geliştirici hata iletisinin metnini belirtir. Daha fazla bilgi için bkz: [#error yönergesi (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).  
  
 Aşağıdaki örnek C1189 oluşturur. Örnekte, çünkü Geliştirici özel hata iletisi sorunları `_WIN32` tanımlayıcısı tanımlı değil:  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 ATL projesinde kullanarak yapılandırdıysanız bu hatayı da görebilirsiniz **/ sağlam** MIDL derleyici seçeneği. Kullanım **/ sağlam** yalnızca oluşturmak için anahtar [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] ve Windows'un sonraki sürümleri. Bu hatayı düzeltmek için aşağıdaki yordamlardan birini kullanın:  
  
-   Bu satırı dlldatax.c dosyasındaki gibi değiştirin:  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 Yeni değer:  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   Kullanım **Gelişmiş** özellik sayfasında **MIDL** kaldırmak için özellik sayfası klasörüne **/ sağlam** geçiş yapın ve ardından belirtin **/no_robust** geçiş yapın. Daha fazla bilgi için bkz: [MIDL özellik sayfaları: Gelişmiş](../../ide/midl-property-pages-advanced.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)