---
title: "Derleyici Hatası C3352 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3352
dev_langs: C++
helpviewer_keywords: C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c0f2effdb6aad3a8015db2280df51bc835d0cf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3352"></a>Derleyici Hatası C3352
'function': Belirtilen işlev temsilci türü 'type' eşleşmiyor  
  
 Parametre listeleri `function` ve temsilci eşleşmiyor.  
  
 Daha fazla bilgi için bkz: [temsilci (C++ bileşen uzantıları)](../../windows/delegate-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3352 oluşturur:  
  
```  
// C3352.cpp  
// compile with: /clr  
delegate int D( int, int );  
ref class C {  
public:  
   int mf( int ) {  
      return 1;  
   }  
  
   // Uncomment the following line to resolve.  
   // int mf(int, int) { return 1; }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352  
}  
```  
