---
title: "Derleyici Hatası C2509 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2509
dev_langs: C++
helpviewer_keywords: C2509
ms.assetid: 339c1fcd-ec4a-456c-9f18-a9b24d9921af
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47a2d3f5bd6cd03195378b55308e052c715c840c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2509"></a>Derleyici Hatası C2509
'tanımlayıcısı': 'sınıfında' bildirilmemiş üye işlevi  
  
 İşlevi belirtilen sınıfında bildirilmedi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2509 oluşturur.  
  
```  
// C2509.cpp  
// compile with: /c  
struct A {  
   virtual int vfunc() = 0;  
   virtual int vfunc2() = 0;  
};  
  
struct B : private A {  
   using A::vfunc;  
   virtual int vfunc2();  
};  
  
int B::vfunc() { return 1; }   // C2509  
int B::vfunc2() { return 1; }   // OK  
```