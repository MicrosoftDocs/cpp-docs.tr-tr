---
title: Bağlayıcı araçları hatası LNK1301 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b4e298ad3815c741ff6c901ac39bf7838ed135d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1301"></a>Bağlayıcı Araçları Hatası LNK1301
LTCG clr modülleri bulunamadı, /LTCG:parameter ile uyumsuz  
  
 /GL ve/CLR ile derlenen bir modül /LTCG (PGO) parametrelerinin profil temelli iyileştirmeler birini birlikte bağlayıcıya geçirildi.  
  
 Profil temelli iyileştirmeler/CLR modülleri için desteklenmez.  
  
 Daha fazla bilgi için bkz.:  
  
-   [/GL (Bütün Program İyileştirmesi)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG (Bağlama Zamanı Kodu Oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)  
  
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