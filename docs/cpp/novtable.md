---
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: 9dcca6ec07a19d53da238020805299b652cbf919
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245160"
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