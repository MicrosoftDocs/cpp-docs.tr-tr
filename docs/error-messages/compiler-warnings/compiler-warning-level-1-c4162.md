---
title: Derleyici Uyarısı (düzey 1) C4162 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4162
dev_langs:
- C++
helpviewer_keywords:
- C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2789f6aa63c8a547a34ec6adfd89c1e1163c68e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33287533"
---
# <a name="compiler-warning-level-1-c4162"></a>Derleyici Uyarısı (düzey 1) C4162
'tanımlayıcısı': bulunan C bağlantısı ile hiçbir işlevi  
  
 C bağlantı işleviyle bildirilmiş ancak bulunamıyor.  
  
 Bu uyarıyı çözmek için derleme .c dosyasında (C Derleyici çağırma).  C++ derleyicisi çağırmanız gerekir, extern "C" işlev bildirimi önce koyun.  
  
 Aşağıdaki örnek C4162 oluşturur  
  
```  
// C4162.cpp  
// compile with: /c /W1  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)   // C4162  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```  
  
 Olası çözüm:  
  
```  
// C4162b.cpp  
// compile with: /c  
extern "C"  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```