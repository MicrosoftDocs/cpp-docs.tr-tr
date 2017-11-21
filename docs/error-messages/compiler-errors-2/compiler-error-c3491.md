---
title: "Derleyici Hatası C3491 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3491
dev_langs: C++
helpviewer_keywords: C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58458a1ab0b67eb4fa6d38d0be2fb38f6d7496eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)