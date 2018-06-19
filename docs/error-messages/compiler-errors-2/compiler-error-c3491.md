---
title: Derleyici Hatası C3491 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3491
dev_langs:
- C++
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bd856f50f3528b3895e4495215b2e479d8a424b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257299"
---
# <a name="compiler-error-c3491"></a>Derleyici Hatası C3491
'var': bir değer tarafından yakalama değişebilir olmayan bir lambda içinde değiştirilemez  
  
 Değişebilir olmayan lambda ifadesi değeri tarafından yakalanan bir değişkenin değeri değiştirilemez.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Lambda ifadesi ile bildirme `mutable` anahtar sözcüğü veya  
  
-   Lambda ifadesi yakalama listesine başvuruya değişkeni geçirin.  
  
## <a name="example"></a>Örnek  
 Yakalama değişkeni değişebilir olmayan lambda ifadesi gövdesi değiştireceği için aşağıdaki örnek C3491 oluşturur `m`:  
  
```  
// C3491a.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) { m = n; }(99); // C3491  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek lambda ifadesi ile bildirerek C3491 çözümler `mutable` anahtar sözcüğü:  
  
```  
// C3491b.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) mutable { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)