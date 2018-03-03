---
title: "Derleyici Hatası C2676 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2676
dev_langs:
- C++
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fad1dce3ca6b707ab8e9e687a5c31b4ecb49d411
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2676"></a>Derleyici Hatası C2676
İkili 'işleci': 'type' değil tanımlamak bu işleci veya kabul edilebilir bir tür dönüşümünü önceden tanımlanmış işleci  
  
 İşleç kullanmak için belirtilen tür için aşırı yükleme veya işleci tanımlandığı bir türe dönüştürme tanımlayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2676 oluşturur.  
  
```  
// C2676.cpp  
// C2676 expected  
struct C {  
   C();  
} c;  
  
struct D {  
   D();  
   D operator >>( C& ){return * new D;}  
   D operator <<( C& ){return * new D;}  
} d;  
  
struct E {  
   // operator int();  
};  
  
int main() {  
   d >> c;  
   d << c;  
   E e1, e2;  
   e1 == e2;   // uncomment operator int in class E, then  
               // it is OK even though neither E::operator==(E) nor   
               // operator==(E, E) defined. Uses the conversion to int   
               // and then the builtin-operator==(int, int)  
}  
```  
  
## <a name="example"></a>Örnek  
 C2676 işaretçi aritmetiği yapmak çalışırsanız da gerçekleşebilir `this` işaretçi başvuru türü.  
  
 `this` İşaretçidir türü tanıtıcının bir başvuru türü. Daha fazla bilgi için bkz: [bu semantiği işaretçi](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 Aşağıdaki örnek C2676 oluşturur.  
  
```  
// C2676_a.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct A {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
  
   A() {  
      Console::WriteLine("{0}", this + 3.3);   // C2676  
      Console::WriteLine("{0}", this[3.3]);   // OK  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
}  
```