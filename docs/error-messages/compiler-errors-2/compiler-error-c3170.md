---
title: Derleyici hatası C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: e2d74a637e2902fcf636b49068882f32aa706f94
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761770"
---
# <a name="compiler-error-c3170"></a>Derleyici hatası C3170

bir projede farklı modül tanımlayıcıları olamaz

derlemedeki iki dosyada farklı adlara sahip [Modül](../../windows/module-cpp.md) öznitelikleri bulundu. Her derleme için yalnızca bir benzersiz `module` özniteliği belirtilebilir.

Özdeş `module` öznitelikleri, birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki modül öznitelikleri bulunursa:

```cpp
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

Ardından,

```cpp
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

Derleyici C3170 oluşturur (farklı adları aklınızda bulunan).
