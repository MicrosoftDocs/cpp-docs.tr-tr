---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3868'
title: Derleyici hatası C3868
ms.date: 11/04/2016
f1_keywords:
- C3868
helpviewer_keywords:
- C3868
ms.assetid: f0e45c2a-2149-4885-a03b-0d230069f03a
ms.openlocfilehash: c71a5321b99e5852a2dc7267dd098bfec08c5ad2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222820"
---
# <a name="compiler-error-c3868"></a>Derleyici hatası C3868

' Type ': ' Parameter ' genel parametresindeki kısıtlamalar bildirimdekilerden farklı

Birden çok bildirim aynı genel kısıtlamalara sahip olmalıdır.  Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3868 oluşturur.

```cpp
// C3868.cpp
// compile with: /clr /c
interface struct I1;

generic <typename T> ref struct MyStruct;
generic <typename U> where U : I1 ref struct MyStruct;   // C3868

// OK
generic <typename T> ref struct MyStruct2;
generic <typename U> ref struct MyStruct2;

generic <typename T> where T : I1 ref struct MyStruct3;
generic <typename U> where U : I1 ref struct MyStruct3;
```
