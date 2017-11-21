---
title: "Bağlayıcı araçları hatası LNK1301 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1301
dev_langs: C++
helpviewer_keywords: LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a01d56f0239160a059fb67774916d9d9aa792709
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1301"></a>Bağlayıcı Araçları Hatası LNK1301
LTCG clr modülleri bulunamadı, /LTCG:parameter ile uyumsuz  
  
 /GL ve/CLR ile derlenen bir modül /LTCG (PGO) parametrelerinin profil temelli iyileştirmeler birini birlikte bağlayıcıya geçirildi.  
  
 Profil temelli iyileştirmeler/CLR modülleri için desteklenmez.  
  
 Daha fazla bilgi için bkz.:  
  
-   [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/ LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Profil temeli iyileştirmeler](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  / CLR ile derleme değil veya /LTCG PGO parametreleri biriyle bağlamayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK1301 oluşturur:  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```