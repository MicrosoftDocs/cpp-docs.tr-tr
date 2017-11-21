---
title: "Derleyici Hatası C3901 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3901
dev_langs: C++
helpviewer_keywords: C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 778bb3336d33c52ce0efcefe96d4da304c1502cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3901"></a>Derleyici Hatası C3901
'accessor_function': dönüş türü 'type' olmalıdır  
  
 En az bir get yöntemin dönüş türü, özellik türü eşleşmesi gerekir. Daha fazla bilgi için bkz: [özelliği](../../windows/property-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3901 oluşturur:  
  
```  
// C3901.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String^ Name {  
      void get();   // C3901  
      // try the following line instead  
      // String^ get();  
   };  
};  
  
ref class Y {  
   property double values[int, int] {  
      int get(int, int);   // C3901  
      // try the following line instead  
      // double get(int, int);  
   };  
};  
```