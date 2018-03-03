---
title: novtable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- novtable_cpp
dev_langs:
- C++
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 26dc6677c6fcc7ab3834d3bb13d9e85dd0d8ede0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bu bir `__declspec` genişletilmiş özniteliğidir.  
  
 Bu `__declspec` formu herhangi bir sınıf bildirimine uygulanabilir, ancak yalnızca saf arabirim sınıflarına, diğer bir deyişle, kendi başlarına örneği oluşturulmayacak sınıflara uygulanmalıdır. `__declspec`, sınıfın oluşturucularında ve yok edicisinde vfptr'yi başlatmak için derleyiciyi durdurarak kod üretmesini engeller. Çoğu durumda bu, yalnızca sınıf ile ilişkili vtable başvurularını kaldırır ve böylece bağlayıcı onu kaldırır. Bu `__declspec` formunu kullanmak kod boyutunda önemli azalmaya neden olabilir.  
  
 `novtable` ile işaretlenmiş bir sınıf örneği oluşturmaya çalışırsanız ve sonra bir sınıf üyesine erişim sağlarsanız, bir erişim ihlali (AV) alırsınız.  
  
## <a name="example"></a>Örnek  
  
```  
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
```Output  
In Y  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)