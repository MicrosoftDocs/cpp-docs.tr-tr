---
title: "Derleyici Uyarısı (Düzey 3) C4738 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30f56b7963d8c6e98d4564ec90adee6bd3d29f9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4738"></a>Derleyici Uyarısı (Düzey 3) C4738
32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı  
  
 C4738 cast, atama sonucu bağımsız değişken geçirildi veya başka bir işlem yuvarlanmasını gerekebilir veya işlemi dışında yazmaçlar çalıştırılmış ve bellek (değişkenlere) kullanmak için gerekli konusunda sizi uyarır. Bu performans kaybına neden olabilir.  
  
 İle bu uyarıyı çözün ve yuvarlama önlemek için derleme [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) veya `double` yerine `float`.  
  
 Bu uyarıyı çözümlemek ve kayıtları tükenmesini önlemek için hesaplama sırasını değiştirmek ve kullanımınızı değiştirmek satır içi kullanım  
  
 Varsayılan olarak bu uyarı kapalıdır. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4738 oluşturur:  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```