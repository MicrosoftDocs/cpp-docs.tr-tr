---
title: "Derleyici Hatası C2217 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2217
dev_langs:
- C++
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6af2bbd43d6e522bbe6ede2a874b7e8ebbf27c10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2217"></a>Derleyici Hatası C2217
'öznitelik1' 'öznitelik2' gerektirir  
  
 İkinci öznitelik ilk işlevi özniteliği gerektirir.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Kesme (`__interrupt`) işlevi bildirilen `near`. Kesme işlevleri olmalıdır `far`.  
  
2.  İşlevi ile bildirilen kesme `__stdcall`, veya `__fastcall`. İşlevler kesme kullanım C çağırma kuralları gerekir.  
  
## <a name="example"></a>Örnek  
 Değişken sayıda bağımsız değişken isteyen bir CLR işlevi bir temsilci bağlanmaya C2217 de ortaya çıkabilir. İşlev e param dizisi aşırı de varsa yerine bunu kullanın. Aşağıdaki örnek C2217 oluşturur.  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```