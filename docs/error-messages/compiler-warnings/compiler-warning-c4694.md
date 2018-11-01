---
title: Derleyici Uyarısı C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: 6eaaa4c1f16e2ac2c5029511430a145fd9b943e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428349"
---
# <a name="compiler-warning-c4694"></a>Derleyici Uyarısı C4694

> '*sınıfı*': kapalı bir soyut sınıf temel sınıf olamaz *$base_class*'

Bir soyut ve korumalı sınıf bir başvuru türünden devralınamaz; mühürlendi ve soyut bir sınıf taban sınıf işlevlerini uygulamak ne kendi temel sınıf olarak kullanılacak izin.

Daha fazla bilgi için [soyut](../../windows/abstract-cpp-component-extensions.md), [korumalı](../../windows/sealed-cpp-component-extensions.md), ve [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md).

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4694 oluşturur.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```