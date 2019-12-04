---
title: Derleyici hatası C3347
ms.date: 11/04/2016
f1_keywords:
- C3347
helpviewer_keywords:
- C3347
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
ms.openlocfilehash: 9f62d66148aa75040f7bab5ea69931d2ef9c474a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755622"
---
# <a name="compiler-error-c3347"></a>Derleyici hatası C3347

' arg ': gerekli bağımsız değişken özniteliğinde belirtilmemiş idl_module

[İdl_module](../../windows/idl-module.md) özniteliğine gerekli bir bağımsız değişken geçirilmedi.

Aşağıdaki örnek C3347 oluşturur:

```cpp
// C3347.cpp
// compile with: /c
[module(name="xx")];

[idl_module(dllname="x")];    // C3347
// try the following line instead
// [idl_module(name="test", dllname="x")];
```
