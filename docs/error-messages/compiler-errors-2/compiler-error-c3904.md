---
title: "Derleyici Hatası C3904 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3904
dev_langs:
- C++
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3aca510cc3caf89625c1dc1d5c1d0890349145e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3904"></a>Derleyici Hatası C3904
'property_accessor': numara parametre belirtmeniz gerekir  
  
 Parametre sayısı denetleyin, `get` ve `set` özelliği boyutları karşı yöntemleri.  
  
-   İçin parametre sayısı `get` yöntemi özelliğinin boyutlarının sayısına eşit veya dizinlenmemiş özellikleri için sıfır olmalıdır.  
  
-   Parametrelerinin sayısı `set` yöntemi olmalı özelliğinin dimensions sayısı'den fazla.  
  
 Daha fazla bilgi için bkz: [özelliği](../../windows/property-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3904 oluşturur.  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3904 oluşturur.  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```