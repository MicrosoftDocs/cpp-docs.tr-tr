---
title: Derleyici Uyarısı (düzey 1) C4566 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4566
dev_langs:
- C++
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8044df3a37e54585f7f3b495b99314e258934f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4566"></a>Derleyici Uyarısı (düzey 1) C4566
evrensel karakter-adı tarafından 'char' temsil karakter geçerli kod sayfasında (sayfa) gösterilemez  
  
 Her Unicode karakteri geçerli ANSI kod sayfasında temsil edilebilir.  
  
 Geniş dizeleri (iki baytlık karakterler) değildir ancak dar dizeleri (tek baytlı karakterler) çok baytlı karakterler dönüştürülür.  
  
 Aşağıdaki örnek C4566 oluşturur:  
  
```  
// C4566.cpp  
// compile with: /W1  
int main() {  
   char c1 = '\u03a0';   // C4566  
   char c2 = '\u0642';   // C4566  
  
   wchar_t c3 = L'\u03a0';   // OK  
   wchar_t c4 = L'\u0642';   // OK  
}  
```