---
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: d101e73f2f8d476c50b1b80b8daa7994151d43af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177839"
---
# <a name="novtable"></a>novtable

**Microsoft 'a özgü**

Bu, **__declspec** genişletilmiş bir özniteliktir.

Bu **__declspec** biçimi herhangi bir sınıf bildirimine uygulanabilir, ancak yalnızca saf arabirim sınıflarına, diğer bir deyişle, kendi kendilerine hiçbir değer oluşturulamamayacak sınıflara uygulanmalıdır. **__Declspec** , derleyicinin oluşturucudaki vfptr 'yi başlatmak için kod üretmesine ve sınıfın yıkıcısında ' a yanıt vermez. Çoğu durumda bu, yalnızca sınıf ile ilişkili vtable başvurularını kaldırır ve böylece bağlayıcı onu kaldırır. Bu **__declspec** biçimini kullanmak kod boyutunda önemli bir azalmaya neden olabilir.

**Novtable** ile işaretlenmiş bir sınıf örneğini oluşturmaya çalışırsanız ve sonra bir sınıf üyesine erişin, bir erişim IHLALI (AV) alırsınız.

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

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
