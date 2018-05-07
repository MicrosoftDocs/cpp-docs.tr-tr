---
title: Derleyici Uyarısı (düzey 1) C4803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c574b51fc13f9224d48495f8b591a56abdc74966
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4803"></a>Derleyici Uyarısı (düzey 1) C4803
'yöntemi': artırma yöntemi, olay farklı depolama sınıfından sahip 'event'  
  
Olay yöntemleri olay bildirimi ile aynı depolama sınıfta olması gerekir. Depolama sınıfları aynı; böylece derleyici olayın yöntemleri ayarlar.  
  
Bir olay bir arabirimi uygulayan bir sınıf varsa, bu uyarı oluşabilir. Derleyici bir arabirim, bir olay için bir yükseltme yöntemi örtük olarak oluşturmaz. Bir sınıfta bu arabirim uyguladığınızda derleyici örtük olarak artırma yöntemi oluşturmak ve bu yöntem bu nedenle sanal olmaz uyarı. Olaylar hakkında daha fazla bilgi için bkz: [olay](../../windows/event-cpp-component-extensions.md).  
  
Bkz: [uyarı](../../preprocessor/warning.md) pragma bir uyarı devre dışı bırakma hakkında bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4803 oluşturur.  
  
```  
// C4803.cpp  
// compile with: /clr /W1  
using namespace System;  
  
public delegate void Del();  
  
ref struct E {  
   Del ^ _pd1;  
   event Del ^ E1 {  
      void add (Del ^ pd1) {  
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));  
      }  
  
      void remove(Del^ pd1) {  
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));  
      }  
  
      virtual void raise() {   // C4803 warning (remove virtual)  
         if (_pd1)  
            _pd1();  
      }  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E ^ ep = gcnew E;  
   ep->E1 += gcnew Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= gcnew Del(ep, &E::func);  
   ep->E1();  
}  
```  
