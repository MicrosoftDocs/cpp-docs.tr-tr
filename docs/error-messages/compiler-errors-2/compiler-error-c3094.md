---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3094'
title: Derleyici hatası C3094
ms.date: 11/04/2016
f1_keywords:
- C3094
helpviewer_keywords:
- C3094
ms.assetid: 10da9b7c-e72d-4013-9925-c83e1bb142db
ms.openlocfilehash: 0ca6beeaf8976aab3847b7384c74f6dfef5a2f5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116346"
---
# <a name="compiler-error-c3094"></a>Derleyici hatası C3094

' Attribute ': anonim kullanıma izin verilmiyor

Bir özniteliğin kapsamı doğru değil.  Daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3094 oluşturur.

```cpp
// C3094.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
public ref class AAttribute : Attribute {};

[A];   // C3094

// OK
[A]
ref class x{};
```
