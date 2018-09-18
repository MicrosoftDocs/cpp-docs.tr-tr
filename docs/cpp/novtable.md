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
ms.openlocfilehash: 2de25452d708545481bdc4a65cab998930b2778e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068441"
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

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)