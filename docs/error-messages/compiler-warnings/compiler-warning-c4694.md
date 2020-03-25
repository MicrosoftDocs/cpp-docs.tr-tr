---
title: Derleyici Uyarısı C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: daf5423588d08260239c3cff5a68532a358d07b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165125"
---
# <a name="compiler-warning-c4694"></a>Derleyici Uyarısı C4694

> '*Class*': kapalı bir soyut sınıf '*BASE_CLASS*' taban sınıfına sahip olamaz

Soyut ve korumalı bir sınıf başvuru türünden devralınabilir; Sealed ve soyut bir sınıf, temel sınıf işlevlerini uygulayabilir ya da kendisinin temel sınıf olarak kullanılmasına izin verebilir.

Daha fazla bilgi için bkz. [soyut](../../extensions/abstract-cpp-component-extensions.md), [korumalı](../../extensions/sealed-cpp-component-extensions.md), ve [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md).

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4694 oluşturur.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```
