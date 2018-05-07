---
title: Derleyici Hatası C3352 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3352
dev_langs:
- C++
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e07b895150896f99cbce9e58e95ffea88f1c9ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
