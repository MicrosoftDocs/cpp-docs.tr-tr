---
title: Derleyici hatası C3133
ms.date: 11/04/2016
f1_keywords:
- C3133
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
ms.openlocfilehash: 003befa97b033eec38d7187966da15e4a275f310
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760718"
---
# <a name="compiler-error-c3133"></a>Derleyici hatası C3133

Öznitelikler varargs 'a C++ uygulanamıyor

Öznitelik yanlış uygulandı. Öznitelikler, değişken bağımsız değişkenlerini temsil eden üç nokta için uygulanamaz.

Daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3133 oluşturur.

```cpp
// C3133.cpp
// compile with: /clr /c
ref struct MyAttr: System::Attribute {};
void Func([MyAttr]...);   // C3133
void Func2([MyAttr] int i);   // OK
```
