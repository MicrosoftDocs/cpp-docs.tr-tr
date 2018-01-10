---
title: "Derleyici Uyarısı (düzey 4) C4481 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4481
dev_langs: C++
helpviewer_keywords: C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52c296251e22adef2702aa9feba2b1fe2bc5122e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4481"></a>Derleyici Uyarısı (düzey 4) C4481
kullanılan standart olmayan uzantısı: override tanımlayıcısı 'anahtar sözcüğü'  
  
 Bir anahtar sözcük c++ standart, örneğin, biri de/CLR altında çalışır geçersiz kılma tanımlayıcılarını olmayan kullanıldı.  Daha fazla bilgi için bkz:  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Geçersiz kılma tanımlayıcıları](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4481 oluşturur.  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```