---
title: Derleyici Hatası C3480 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3480
dev_langs:
- C++
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 673eff58b09fe1f2bbfe8a7629594399e8ca6b22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33259145"
---
# <a name="compiler-error-c3480"></a>Derleyici Hatası C3480
'var': kapsayan bir işlev kapsamdan bir lambda yakalama değişken olmalıdır  
  
 Lambda yakalama değişkeni kapsayan bir işlev kapsamından değil.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Değişkeni lambda ifadesi yakalama listesinden kaldırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3480 oluşturur çünkü değişkeni `global` kapsayan bir işlev kapsamından değil:  
  
```  
// C3480a.cpp  
  
int global = 0;  
int main()  
{  
   [&global] { global = 5; }(); // C3480  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek değişkeni kaldırarak C3480 çözümler `global` lambda ifadesi yakalama listesinden:  
  
```  
// C3480b.cpp  
  
int global = 0;  
int main()  
{  
   [] { global = 5; }();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)