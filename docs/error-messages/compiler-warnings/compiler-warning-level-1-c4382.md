---
title: Derleyici Uyarısı (düzey 1) C4382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4382
dev_langs:
- C++
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c02f0cb2d22aebb9af31844aec3bf68b97c3442e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4382"></a>Derleyici Uyarısı (düzey 1) C4382
'type' atma: / CLR __clrcall yıkıcı veya kopya Oluşturucu türüyle yalnızca yakalanabilir: Saf Modülü  
  
 **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışıdır.  
  
 İle derlendiğinde **/CLR** (değil **/CLR: pure**), özel durum işleme olacak şekilde, bir yerel tür üye işlevleri bekliyor [__cdecl](../../cpp/cdecl.md) ve [__clrcall](../../cpp/clrcall.md). Üye işlevlerini kullanarak ile yerel türler `__clrcall` çağırma olamaz yakalanan ile derlenmiş bir modülde **/CLR**.  
  
 Özel durum ile derlenmiş bir modülde yakalandı varsa **/CLR: pure**, bu uyarıyı yoksayabilirsiniz.  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4382 oluşturur.  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```