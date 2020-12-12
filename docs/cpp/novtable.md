---
description: 'Daha fazla bilgi edinin: novtable'
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: 2c818d07603e294f760b768861ce7e7a3e02894b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146204"
---
# <a name="novtable"></a>novtable

**Microsoft'a Özgü**

Bu genişletilmiş bir **`__declspec`** özniteliktir.

Bu form **`__declspec`** herhangi bir sınıf bildirimine uygulanabilir, ancak yalnızca saf arabirim sınıflarına, diğer bir deyişle, kendi kendilerine hiçbir değer oluşturulamamayacak sınıflara uygulanmalıdır. , **`__declspec`** Derleyicinin Oluşturucu ve sınıf yıkıcısında vfptr 'yi başlatmak için kod oluşturmasını engeller. Çoğu durumda bu, yalnızca sınıf ile ilişkili vtable başvurularını kaldırır ve böylece bağlayıcı onu kaldırır. Bu formun kullanılması **`__declspec`** kod boyutunda önemli bir azalmaya neden olabilir.

İle işaretlenmiş bir sınıf örneğini oluşturmaya **`novtable`** ve ardından bir sınıf üyesine erişime çalışırsanız, bir erişim ihlali (AV) alırsınız.

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`__declspec`](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
