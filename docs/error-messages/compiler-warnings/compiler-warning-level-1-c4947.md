---
title: "Derleyici Uyarısı (düzey 1) C4947 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4947
dev_langs: C++
helpviewer_keywords: C4947
ms.assetid: 5a1d484e-b4c7-4de2-a145-d8dcfc2fc1d2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9e0f02401fc9af9d9337b939b8acc33f290252d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4947"></a>Derleyici Uyarısı (düzey 1) C4947
'type_or_member': kullanımdan kaldırılmış olarak işaretlenmiş  
  
Bir üye ya da türü ile kullanımdan kaldırılmış olarak işaretlenmiş <xref:System.ObsoleteAttribute> sınıfı.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C4947 oluşturur:  
  
```cpp  
// C4947.cpp  
// compile with: /clr /W1  
// C4947 expected  
using namespace System;  
  
[System::ObsoleteAttribute]  
ref struct S {  
   [System::ObsoleteAttribute]  
   int i;  
  
   [System::ObsoleteAttribute]  
   void mFunc(){}  
};  
  
// Any reference to Func1 should generate a warning  
[System::ObsoleteAttribute]  
Int32 Func1(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
// Any reference to Func2 should generate a warning with  message  
[System::ObsoleteAttribute("Will be removed in next version")]  
Int32 Func2(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
int main() {  
   Int32 MyInt1 = ::Func1(2, 2);  
   Int32 MyInt2 = ::Func2(2, 2);  
  
   S^ s = gcnew S();  
   s->i = 10;  
   s->mFunc();  
}  
```