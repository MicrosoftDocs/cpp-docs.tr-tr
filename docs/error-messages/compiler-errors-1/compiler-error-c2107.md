---
title: Derleyici Hatası C2107 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2107
dev_langs:
- C++
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a4d173162d290644f450614e19aaa96615c0ae2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2107"></a>Derleyici Hatası C2107
Geçersiz dizin, yöneltme izin verilmiyor  
  
 Bir alt simge gösteren bir işaretçi değerlendirmez bir ifade uygulanır.  
  
## <a name="example"></a>Örnek  
 C2107 yanlış kullanırsanız oluşabilir `this` işaretçi türünün varsayılan dizin oluşturucu erişmek için bir değer türü. Daha fazla bilgi için bkz: [bu semantiği işaretçi](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 Aşağıdaki örnek C2107 oluşturur.  
  
```  
// C2107.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property String ^ default[String ^] {  
      String ^ get(String ^ data) {  
         return "abc";  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this["aa"]);   // C2107  
      Console::WriteLine("{0}", this->default["aa"]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```