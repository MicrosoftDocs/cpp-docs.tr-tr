---
title: Derleyici Hatası C3490 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 593e5509ada926f27243a761da3470eb2d846a22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3490"></a>Derleyici Hatası C3490
const nesnesi aracılığıyla erişilen için 'var' değiştirilemiyor  
  
 İçinde bildirilen bir lambda ifadesi bir `const` yöntemi değişebilir olmayan üye verileri değiştiremez.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kaldırma `const` değiştirici yöntem bildirimi gelen.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, C3490 oluşturur, üye değişkeni değiştirdiğinden `_i` içinde bir `const` yöntemi:  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kaldırarak C3490 çözümler `const` değiştirici yöntem bildirimi gelen:  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)