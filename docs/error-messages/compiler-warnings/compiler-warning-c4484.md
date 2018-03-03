---
title: "Derleyici Uyarısı C4484 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa5f209dd3a77bcc4ec3c21d589fb8ba1ed3faf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4484"></a>Derleyici Uyarısı C4484
'override_function': temel ref sınıf yöntemi 'base_class_function' ile eşleşir, ancak 'sanal', 'new' veya 'override'; işaretlenmedi 'Yeni' (ve 'sanal') kabul edilir  
  
 İle derleme yapılırken **/CLR**, derleyici örtük olarak işlev vtable'de yeni yuva alırsınız anlamına gelir bir temel sınıf işlevi üzerine yazılmaz. Çözmek için açıkça bir işlevi geçersiz kılma olup olmadığını belirtin.  
  
 Daha fazla bilgi için bkz.:  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [Yeni (vtable'de yeni yuva)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 her zaman hata olarak verilir. Kullanım [uyarı](../../preprocessor/warning.md) C4484 gizlemek için pragması.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4484 oluşturur.  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```