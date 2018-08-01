---
title: novtable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- novtable_cpp
dev_langs:
- C++
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5deee0209866580afd038fbce068a9275f5b5874
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406974"
---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bu bir **__declspec** genişletilmiş öznitelik.  
  
 Bu tür **__declspec** herhangi bir sınıf bildirimine uygulanabilir, ancak yalnızca saf arabirim sınıflarına, diğer bir deyişle, hiçbir zaman kendi başlarına örneği oluşturulur sınıfları uygulanmalıdır. **__Declspec** oluşturucularında ve yok edicisinde vfptr'yi başlatmak için kod oluşturma derleyicinin durdurur. Çoğu durumda bu, yalnızca sınıf ile ilişkili vtable başvurularını kaldırır ve böylece bağlayıcı onu kaldırır. Bu biçimi kullanarak **__declspec** kod boyutunda önemli azalmaya neden olabilir.  
  
 İle işaretlenmiş bir sınıf örneği çalışırsanız **novtable** ve ardından bir sınıf üyesine erişim sağlarsanız, erişim ihlali (AV) alırsınız.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)