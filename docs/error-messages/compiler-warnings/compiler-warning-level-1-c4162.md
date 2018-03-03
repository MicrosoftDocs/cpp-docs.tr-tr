---
title: "Derleyici Uyarısı (düzey 1) C4162 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4162
dev_langs:
- C++
helpviewer_keywords:
- C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 980c2229b06e5c7bef85901daaa788a6a2911ee3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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