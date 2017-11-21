---
title: "Derleyici Uyarısı (düzey 1) C4002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4002
dev_langs: C++
helpviewer_keywords: C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bb1e3512074b2767977367b30ac5d01dc5758b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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