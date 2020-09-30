---
title: Derleyici hatası C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: c4eb4a2551312791d05c8badb66af0070e74b630
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508324"
---
# <a name="compiler-error-c3170"></a>Derleyici hatası C3170

bir projede farklı modül tanımlayıcıları olamaz

derlemedeki iki dosyada farklı adlara sahip [Modül](../../windows/attributes/module-cpp.md) öznitelikleri bulundu. `module`Her derleme için yalnızca bir benzersiz öznitelik belirtilebilir.

Aynı `module` öznitelikler birden fazla kaynak kodu dosyasında belirtilebilir.

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
