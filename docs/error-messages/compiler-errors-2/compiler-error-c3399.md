---
title: Derleyici Hatası C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: e400c181f987a83588f8aedc63ecdedb82be310f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568690"
---
# <a name="compiler-error-c3399"></a>Derleyici Hatası C3399

'type': bir genel parametrenin örneği oluşturulurken bağımsız değişken sağlanamaz

Belirttiğinizde `gcnew()` kısıtlaması, belirttiğiniz kısıtlama türü parametresiz bir oluşturucu gerekir. Bu nedenle, bu tür örneği ve bir parametre geçirin denemek için bir hatadır.

Bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3399 oluşturur.

```
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```