---
title: Derleyici hatası C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: d20b5e816930969278536fe3771df4ad38c3c86b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737523"
---
# <a name="compiler-error-c3399"></a>Derleyici hatası C3399

' Type ': bir genel parametrenin örneği oluşturulurken bağımsız değişken sağlayamaz

`gcnew()` kısıtlamasını belirttiğinizde, kısıtlama türünün parametresiz bir Oluşturucusu olacağını belirtirsiniz. Bu nedenle, bu tür örneği oluşturma ve bir parametre geçirme girişimi bir hatadır.

Daha fazla bilgi için bkz. [genelC++tür parametrelerindeki kısıtlamalar (/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3399 oluşturur.

```cpp
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```
