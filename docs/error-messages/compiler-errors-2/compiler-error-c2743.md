---
title: Derleyici Hatası C2743 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a762a7c816f713f9371ff50524ccb582753535b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2743"></a>Derleyici Hatası C2743
'type': catch __clrcall yıkıcı veya kopya Oluşturucu ile yerel bir türü olamaz  
  
 İle bir modül derlenmiş **/CLR** yerel tür ve burada tür yıkıcı veya kopya Oluşturucu kullanan bir özel durum catch çalışıldı `__clrcall` çağırma.  
  
 İle derlendiğinde **/CLR**, özel durum işleme olacak şekilde, bir yerel tür üye işlevleri bekliyor [__cdecl](../../cpp/cdecl.md) ve [__clrcall](../../cpp/clrcall.md). Üye işlevlerini kullanarak ile yerel türler `__clrcall` çağırma olamaz yakalanan ile derlenmiş bir modülde **/CLR**.  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2743 oluşturur.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```