---
title: "Derleyici Hatası C3804 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3804
dev_langs: C++
helpviewer_keywords: C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01952fa59be1fe64d6c8b8c7392a09ab9ac327c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3804"></a>Derleyici Hatası C3804
'property_accessor': erişimci yöntemleri bir özellik ya da gerekir için tüm statik veya tüm statik olmayan  
  
 Önemsiz olmayan bir özellik tanımlarken erişimci işlevleri ya da statik olabilir veya örneği, ancak ikisine birden değil.  
  
 Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3804 oluşturur.  
  
```  
// C3804.cpp  
// compile with: /c /clr  
ref struct A {  
  
   property int i {  
      static int get() {}  
      void set(int i) {}  
   }   // C3804 error  
  
   // OK  
   property int j {  
      int get() { return 0; }  
      void set(int i) {}  
   }  
  
   property int k {  
      static int get() { return 0; }  
      static void set(int i) {}  
   }  
};  
```