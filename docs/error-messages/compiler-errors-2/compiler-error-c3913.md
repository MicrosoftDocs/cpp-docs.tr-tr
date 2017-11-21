---
title: "Derleyici Hatası C3913 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3913
dev_langs: C++
helpviewer_keywords: C3913
ms.assetid: a678bfce-9524-470d-9f23-7d08ecb972c8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ad34e5b74be2b19d0638f6f4b42b6f3a0cf4ab78
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3913"></a>Derleyici Hatası C3913
Varsayılan özellik dizine gerekir  
  
 Varsayılan bir özellik yanlış tanımlandı.  
  
 Daha fazla bilgi için bkz: [özelliği](../../windows/property-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3913 oluşturur:  
  
```  
// C3913.cpp  
// compile with: /clr /c  
ref struct X {  
   property int default {   // C3913  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```