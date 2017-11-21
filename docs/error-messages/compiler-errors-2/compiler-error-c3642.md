---
title: "Derleyici Hatası C3642 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3642
dev_langs: C++
helpviewer_keywords: C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4b5d73344b99a42dfc4caf2b9f6b8cf7c9dc18bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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