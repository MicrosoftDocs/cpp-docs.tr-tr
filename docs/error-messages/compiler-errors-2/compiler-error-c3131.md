---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3131'
title: Derleyici hatası C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: 3fde5045f2c14efdac96f902e12dcea1f5118505
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177412"
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
