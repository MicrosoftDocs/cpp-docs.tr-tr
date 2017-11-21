---
title: "Derleyici Hatası C2296 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2296
dev_langs: C++
helpviewer_keywords: C2296
ms.assetid: 47d270f4-13ce-4c16-81e2-7d67c6c4a540
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e915df8a0ab9a9baa5b314f850434e41087be8b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2296"></a>Derleyici Hatası C2296
'işleci': hatalı sol işleneni  
  
 İle kullanılan sol işleneni `operator` geçersiz.  
  
 Örneğin, derleyici, bir işlev çağrısı istendiği bir bildirim görebilirsiniz.  
  
 Aşağıdaki örnek C2296 oluşturur:  
  
```  
// C2296.cpp  
struct MyStruct {  
   struct Help {  
      Help(float f) : m_f(f) {}  
      float m_f;  
   };  
  
   MyStruct(const Help &h) : m_f(h.m_f) {}  
   MyStruct(float f) : m_f(f) {}  
   MyStruct operator*(const MyStruct &f1) const {   
      return MyStruct(m_f * f1.m_f);  
   }  
  
private:  
   float m_f;  
};  
  
int main() {  
   float f1 = 1.0f;  
  
   MyStruct m_MyStruct1 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct1 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct2 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct2 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2296  
}  
```