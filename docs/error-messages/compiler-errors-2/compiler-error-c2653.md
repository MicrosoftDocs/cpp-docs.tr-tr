---
title: "Derleyici Hatası C2653 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2653
dev_langs: C++
helpviewer_keywords: C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b2cca7e855256e9caf5a72e6f8b4a6e2924eca6
ms.sourcegitcommit: 78f3f8208d49b7c1d87f4240f4a1496b7c29333e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2017
---
# <a name="compiler-error-c2653"></a>Derleyici Hatası C2653
'tanımlayıcısı': bir sınıf veya ad alanı adı değil  
  
Sınıf, yapı, UNION veya ad alanı adı sözdizimi gerektirir.  
  
Aşağıdaki örnek C2653 oluşturur:  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 tanımlamak çalışırsanız olası ayrıca bir *bileşik ad alanı*, Visual Studio 2015 güncelleştirme 3'ü önce Visual C++ sürümünü kullandığınızda, bir veya daha fazla kapsam iç içe geçmiş ad alanı adlarını içeren bir ad alanı. Bileşik ad alanı tanımları C++ C ++ 17 önce izin verilmez. Visual C++ 2015 sürüm 15,5 başlayarak, derleyici bileşik ad alanı tanımları destekler, [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) derleyici seçeneği belirtildi:  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++17 to fix (or /std:c++latest in 15.3)
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  

İçinde Visual Studio 2017 sürüm 15.3, / Std: c ++ son anahtarı gereklidir.
