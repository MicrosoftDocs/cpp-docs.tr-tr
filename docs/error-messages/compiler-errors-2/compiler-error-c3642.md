---
title: Derleyici Hatası C3642 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3642
dev_langs:
- C++
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9e841bcc4fbcb62d6a2d1e6f51f47a73bd2e06a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264523"
---
# <a name="compiler-error-c3642"></a>Derleyici Hatası C3642
' Döndür_tür/bağımsız değişken': bir işlev çağırma yerel koddan __clrcall ile çağrılamaz  
  
 İle işaretlenen bir işlev [__clrcall](../../cpp/clrcall.md) çağırma kuralı (yönetilmeyen) yerel koddan çağrılamaz.  
  
 *Döndür_tür/args* işlevin adını ya da türünü `__clrcall` çağrısı çalıştığınız işlevi.  İşlev işaretçisi çağrılırken bir türü kullanılır.  
  
 Yerel bir bağlamından yönetilen bir işlevi çağırmak için çağıracak bir "sarmalayıcı" işlev ekleyebilirsiniz `__clrcall` işlevi. Veya, CLR düzenleme mekanizması kullanabilirsiniz; bkz: [nasıl yapılır: sıralama işlevi işaretçileri PInvoke kullanarak](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C3642 oluşturur:  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```