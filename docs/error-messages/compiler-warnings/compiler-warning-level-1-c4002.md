---
title: Derleyici Uyarısı (düzey 1) C4002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4002
dev_langs:
- C++
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa1943000becde663fbb0da445f861f408f01f9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4002"></a>Derleyici Uyarısı (düzey 1) C4002
Makro 'tanımlayıcısı' için çok fazla gerçek parametreleri  
  
 Makro gerçek parametre sayısı makro tanımı'ndaki resmi parametre sayısını aşıyor. Önişlemci toplar ek parametreler ancak yoksayar bunları makrosu genişletme sırasında.  
  
 C4002 yanlış kullanılırken oluşabilir [Variadic makrolar](../../preprocessor/variadic-macros.md).  
  
 Aşağıdaki örnek C4002 oluşturur:  
  
```  
// C4002.cpp  
// compile with: /W1  
#define test(a) (a)  
  
int main() {  
   int a = 1;  
   int b = 2;  
   a = test(a,b);   // C4002  
   // try..  
   a = test(a);  
}  
```  
  
 Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucunda da oluşturulabilir: artık kabul makrosu fazladan virgül kullanımı.  
  
 Derleyici artık makro fazladan virgül kullanımı kabul eder. Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümü geçerli olması kod için fazladan virgül kaldırın.  
  
```  
// C4002b.cpp  
// compile with: /W1  
#define F(x,y)  
int main()  
{  
   F(2,,,,,,3,,,,,,)   // C4002  
   // Try the following line instead:  
   // F(2,3)  
}  
```