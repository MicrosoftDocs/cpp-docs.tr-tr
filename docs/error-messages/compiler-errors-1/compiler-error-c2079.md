---
title: Derleyici Hatası C2079 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2079
dev_langs:
- C++
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b29200be08c10dcfaeb178941309c6f3aec6ff9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2079"></a>Derleyici Hatası C2079
'tanımlayıcı' tanımsız sınıfı/struct/union 'name' kullanır  
  
 Belirtilen tanımlayıcı bir tanımsız sınıf, yapı veya birleşim değil.  
  
 Bu hata anonim bir birleşim başlatarak neden olabilir.  
  
 Aşağıdaki örnek C2079 oluşturur:  
  
```  
// C2079.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   std::ifstream g;   // C2079  
}  
```  
  
 Olası çözüm:  
  
```  
// C2079b.cpp  
// compile with: /EHsc  
#include <fstream>  
int main( ) {  
   std::ifstream g;  
}  
```  
  
 Yığında, ileriye dönük bildirimi yalnızca kapsamında olan bir türde bir nesne bildirme çalışırsanız C2079 da oluşabilir.  
  
```  
// C2079c.cpp  
class A;  
  
class B {  
   A a;   // C2079  
};  
  
class A {};  
```  
  
 Olası çözüm:  
  
```  
// C2079d.cpp  
// compile with: /c  
class A;  
class C {};  
  
class B {  
   A * a;  
   C c;  
};  
  
class A {};  
```