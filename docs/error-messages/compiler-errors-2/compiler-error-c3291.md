---
title: Derleyici hatası C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: eb98be3677de6c93fdb7bedf7c0d482115891697
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760146"
---
# <a name="compiler-error-c3291"></a>Derleyici hatası C3291

' default ': önemsiz bir özelliğin adı olamaz

Önemsiz bir özellik `default`olarak adlandırılamaz. Daha fazla bilgi için bkz. [özelliği](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3291 oluşturur.

```cpp
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```
