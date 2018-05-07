---
title: Derleyici Uyarısı C4485 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4485
dev_langs:
- C++
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b84d2976e31d5cc3a9b6547d0c4b02a61327ce0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4485"></a>Derleyici Uyarısı C4485
'override_function': temel ref sınıf yöntemi 'base_class_function' ile eşleşir, ancak işaretlenen 'Yeni' veya 'override'; 'Yeni' (ve 'sanal') kabul edilir  
  
 Erişimci, ile veya olmadan geçersiz kılmaları `virtual` anahtar sözcük, bir taban sınıf erişimci işlevi ancak `override` veya `new` tanımlayıcısı geçersiz kılma işlev imzası parçası değil. Ekleme `new` veya `override` bu uyarıyı çözümlemek için tanımlayıcısı.  
  
 Bkz: [geçersiz kılma](../../windows/override-cpp-component-extensions.md) ve [yeni (vtable'de yeni yuva)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md) daha fazla bilgi için.  
  
 C4485 her zaman hata olarak verilir. Kullanım [uyarı](../../preprocessor/warning.md) C4485 gizlemek için pragması.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4485 oluşturur  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```