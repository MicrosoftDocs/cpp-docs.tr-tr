---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3133'
title: Derleyici hatası C3133
ms.date: 11/04/2016
f1_keywords:
- C3133
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
ms.openlocfilehash: 3559e5864ea5f8d5e690a77899d6314ee2b65519
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177386"
---
# <a name="compiler-error-c3133"></a>Derleyici hatası C3133

Öznitelikler C++ vararg 'larına uygulanamaz

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
