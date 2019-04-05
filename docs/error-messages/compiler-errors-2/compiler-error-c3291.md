---
title: Derleyici Hatası C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: e3f20d7d7e63079ed9c7a078e9fc9eac06d32677
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781620"
---
# <a name="compiler-error-c3291"></a>Derleyici Hatası C3291

'default': Önemsiz bir özelliğin adı olamaz

Önemsiz özellik adlı `default`. Bkz: [özelliği](../../extensions/property-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3291 oluşturur.

```
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```