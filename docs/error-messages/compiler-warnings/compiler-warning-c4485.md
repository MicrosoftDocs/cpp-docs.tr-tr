---
title: "Derleyici Uyarısı C4485 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4485
dev_langs: C++
helpviewer_keywords: C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 435e49a857e3c448ac7e5f7ef00bb9032320aa25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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