---
title: Derleyici Uyarısı C4484 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75531c207f0136f16109b4d69d689b883998aae2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274761"
---
# <a name="compiler-warning-c4484"></a>Derleyici Uyarısı C4484
'override_function': temel ref sınıf yöntemi 'base_class_function' ile eşleşir, ancak 'sanal', 'new' veya 'override'; işaretlenmedi 'Yeni' (ve 'sanal') kabul edilir  
  
 İle derleme yapılırken **/CLR**, derleyici örtük olarak işlev vtable'de yeni yuva alırsınız anlamına gelir bir temel sınıf işlevi üzerine yazılmaz. Çözmek için açıkça bir işlevi geçersiz kılma olup olmadığını belirtin.  
  
 Daha fazla bilgi için bkz.:  
  
-   [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
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