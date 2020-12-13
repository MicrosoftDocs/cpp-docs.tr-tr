---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3291'
title: Derleyici hatası C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: 4fcaa080167ae8ef63ffd7b1b180a74e29ac6411
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144748"
---
# <a name="compiler-error-c3291"></a>Derleyici hatası C3291

' default ': önemsiz bir özelliğin adı olamaz

Önemsiz bir özellik adlandırılamaz **`default`** . Daha fazla bilgi için bkz. [özelliği](../../extensions/property-cpp-component-extensions.md) .

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
