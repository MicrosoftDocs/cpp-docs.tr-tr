---
title: "Derleyici Uyarısı (Düzey 3) C4101 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 162ad70f6d87ba6de51f677d95f1af7c1b6d8054
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4101"></a>Derleyici Uyarısı (Düzey 3) C4101
'tanımlayıcısı': başvurulmayan yerel değişken  
  
 Yerel değişken asla kullanılmaz. Bu uyarı açık durumda ortaya çıkar:  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 Ancak, bu uyarıyı çağrılırken oluşacaktır bir **statik** üye işlevi sınıfının bir örneği ile:  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 Bu durumda, derleyici hakkında bilgileri kullanır `si` erişimi **statik** işlevi, ancak sınıf örneği gerekli olmadığında çağırmak için **statik** işlev; bu nedenle uyarı. Bu uyarıyı çözmek için şunları yapabilir:  
  
-   İçinde derleyici kullandığınız örneğini bir oluşturucu ekleyin `si` çağrısında `func`.  
  
-   Kaldırma **statik** anahtar sözcüğü tanımından `func`.  
  
-   Çağrı **statik** açıkça işlev: `int y = S::func();`.