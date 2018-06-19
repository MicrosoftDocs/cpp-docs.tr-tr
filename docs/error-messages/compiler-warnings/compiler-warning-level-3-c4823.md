---
title: Derleyici Uyarısı (Düzey 3) C4823 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c29499a82601dcf653ff2f003441935f1d6841a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293237"
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
