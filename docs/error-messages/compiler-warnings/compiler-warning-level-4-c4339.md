---
title: "Derleyici Uyarısı (düzey 4) C4339 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4339
dev_langs: C++
helpviewer_keywords: C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 48906dbea56c3408384a31e9855a8ac31abd5f37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4339"></a>Derleyici Uyarısı (düzey 4) C4339
'type': Tanımsız Tür kullanımını algılandı WinRT veya CLR meta veri - bu türün kullanımı, bir çalışma zamanı özel durumuna neden olabilir  
  
 Windows çalışma zamanı veya ortak dil çalışma zamanı için derlenen kodda bir türü tanımlanmadı. Olası çalışma zamanı özel durumu önlemek için türünü tanımlayın.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4339 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C4339.cpp  
// compile with: /W4 /clr /c  
// C4339 expected  
#pragma warning(default : 4339)  
  
// Delete the following line to resolve.  
class A;  
  
// Uncomment the following line to resolve.  
// class A{};  
  
class X {  
public:  
   X() {}  
  
   virtual A *mf() {  
      return 0;  
   }  
};  
  
X * f() {  
   return new X();  
}  
```