---
title: Derleyici hatası C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: e19442e3c218ade2fc9f9b1c18bf44ade8188035
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501428"
---
# <a name="compiler-error-c3131"></a>Derleyici hatası C3131

Projenin ' name ' özelliği olan bir ' Module ' özniteliği olmalıdır

[Modül](../../windows/attributes/module-cpp.md) özniteliğinin bir Name parametresi olmalıdır.

Aşağıdaki örnek C3131 oluşturur:

```cpp
// C3131.cpp
[emitidl];
[module];   // C3131
// try the following line instead
// [module (name="MyLib")];

[public]
typedef long int LongInt;
```
