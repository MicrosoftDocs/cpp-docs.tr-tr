---
title: _SCL_SECURE_NO_WARNINGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs: C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 288af808dfa714c10eeba1f11738cf9db31d70d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS
C++ Standart Kitaplığı'nda olmayabilecek yöntemlerden birini çağırma neden olur [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Bu uyarıyı devre dışı bırakmak için makrosu tanımlama **_SCL_SECURE_NO_WARNINGS** kodunuzda:  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Uyarı C4996 devre dışı bırakmak için diğer yolları şunlardır:  
  
-   Kullanarak [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md) derleyici seçeneği:  
  
 ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
```  
  
-   Kullanarak [/w](../build/reference/compiler-option-warning-level.md) derleyici seçeneği:  
  
 ```  
    cl /wd4996 [other compiler options] myfile.cpp  
```  
  
-   Kullanarak [#pragma Uyarısı](../preprocessor/warning.md) yönergesi:  
  
 ```  
 #pragma warning(disable:4996)  
```  
  
 Ayrıca, el ile birlikte C4996 uyarı düzeyini değiştirebilirsiniz **/w\<l >\< n>**  derleyici seçeneği. Örneğin, düzey 4 C4996 uyarı ayarlamak için şunu yazın:  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 Daha fazla bilgi için bkz: [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](../build/reference/compiler-option-warning-level.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenli Kitaplıklar: C++ Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md)

