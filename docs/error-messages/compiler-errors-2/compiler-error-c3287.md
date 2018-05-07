---
title: Derleyici Hatası C3287 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3287
dev_langs:
- C++
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66952d5900338ec6840971678c2bbea2ebcf6bff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3287"></a>Derleyici Hatası C3287
' % s'type 'türü' (GetEnumerator dönüş türü) bir uygun ortak MoveNext üye işlevini ve ortak geçerli özellik olmalıdır  
  
 Kullanıcı tanımlı koleksiyon sınıfları tanımlarını içermelidir `MoveNext` ve `Current`.  
  
 Bkz: [nasıl yapılır: her Iterate Over a User-Defined koleksiyonuyla](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3287 oluşturur.  
  
```  
// C3287.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {  
   bool MoveNext() {  
      return true;  
   }  
   property Object^ Current {  
      Object^ get() {  
         Object ^ o = gcnew Object;  
         return o;  
      }  
   }  
};  
  
ref struct R2 {  
   R ^GetEnumerator() {  
      R^ r = gcnew R;  
      return r;  
   }  
};  
  
ref struct T {};  
  
ref struct T2 {  
   T ^GetEnumerator() {  
      T^ t = gcnew T;  
      return t;  
   }  
};  
  
int main() {  
   for each (int i in gcnew T2) {}   // C3287  
   for each (int i in gcnew R2) {}   // OK  
}  
```