---
title: "Derleyici Uyarısı (Düzey 3) C4823 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4823
dev_langs: C++
helpviewer_keywords: C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af4b7e220957722793458a283244092574d05fa9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4823"></a>Derleyici Uyarısı (Düzey 3) C4823
'function': sabitleme işaretçileri ancak bırakma kullanır semantiği etkin değil. /EHa kullanmayı düşünün  
  
Nesnenin blok kapsamında bildirilen sabitleme işaretçisi işaret yönetilen yığında çıkarmak için derleyici "işaretçinin nullifies yıkıcı sabitleme işaretçiyle davranan" yerel sınıfların Yıkıcılar davranışını taklit eder. Bir özel durum atma sonra yapılan bir çağrı etkinleştirmek için nesneyi geriye doğru izleme, kullanarak bunu yapabilirsiniz etkinleştirmelisiniz [/EHsc](../../build/reference/eh-exception-handling-model.md).  
  
El ile de nesne sabitleme ve uyarıyı yok sayın.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C4823 oluşturur.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  
