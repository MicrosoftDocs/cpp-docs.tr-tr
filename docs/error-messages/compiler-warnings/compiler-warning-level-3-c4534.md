---
title: Derleyici Uyarısı (Düzey 3) C4534 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b765f5f654c8d533b0ae22d874e7657cd10d667
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4534"></a>Derleyici Uyarısı (Düzey 3) C4534
'Oluşturucusu' class 'sınıfı nedeniyle varsayılan bağımsız değişkeni için varsayılan bir oluşturucu olmayacaktır.  
  
 Yönetilmeyen bir sınıf varsayılan değerlere sahip parametrelere sahip bir oluşturucuya sahip olabilir ve derleyici bu varsayılan oluşturucu kullanır. Bir sınıf olarak `value` anahtar sözcüğü kullanmaz bir oluşturucu varsayılan değerlerle parametreleri için varsayılan bir oluşturucu.  
  
 Daha fazla bilgi için bkz: [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C4534 oluşturur:  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```