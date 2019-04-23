---
title: Derleyici Hatası C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: d05a861a2baedb86482503b6860098f12c41bd78
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776463"
---
# <a name="compiler-error-c3399"></a>Derleyici Hatası C3399

'type': bir genel parametrenin örneği oluşturulurken bağımsız değişken sağlanamaz

Belirttiğinizde `gcnew()` kısıtlaması, belirttiğiniz kısıtlama türü parametresiz bir oluşturucu gerekir. Bu nedenle, bu tür örneği ve bir parametre geçirin denemek için bir hatadır.

Bkz: [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) daha fazla bilgi için.

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