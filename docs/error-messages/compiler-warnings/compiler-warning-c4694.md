---
title: Derleyici Uyarısı C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: 6164fd2e19e35233ba67feb84d117f1e4e01f20d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778845"
---
# <a name="compiler-warning-c4694"></a>Derleyici Uyarısı C4694

> '*sınıfı*': kapalı bir soyut sınıf temel sınıf olamaz *$base_class*'

Bir soyut ve korumalı sınıf bir başvuru türünden devralınamaz; mühürlendi ve soyut bir sınıf taban sınıf işlevlerini uygulamak ne kendi temel sınıf olarak kullanılacak izin.

Daha fazla bilgi için [soyut](../../extensions/abstract-cpp-component-extensions.md), [korumalı](../../extensions/sealed-cpp-component-extensions.md), ve [sınıfları ve yapıları](../../extensions/classes-and-structs-cpp-component-extensions.md).

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4694 oluşturur.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```