---
title: Derleyici Uyarısı (Düzey 3) C4101 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 973b966e4b589cb35ffc92da9031779b14d448e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291121"
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