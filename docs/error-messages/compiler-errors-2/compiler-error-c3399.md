---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3399'
title: Derleyici hatası C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: a950857e88c5cfcad50ac2efb064af4d7a5c0cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316433"
---
# <a name="compiler-error-c3399"></a>Derleyici hatası C3399

' Type ': bir genel parametrenin örneği oluşturulurken bağımsız değişken sağlayamaz

`gcnew()`Kısıtlama belirttiğinizde, kısıtlama türünün parametresiz bir Oluşturucusu olacağını belirtirsiniz. Bu nedenle, bu tür örneği oluşturma ve bir parametre geçirme girişimi bir hatadır.

Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

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
