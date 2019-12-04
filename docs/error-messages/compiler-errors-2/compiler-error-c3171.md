---
title: Derleyici hatası C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: a3af19fa6b4f4def9bb42325f648109cfafcdaef
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761757"
---
# <a name="compiler-error-c3171"></a>Derleyici hatası C3171

' Module ': bir projede farklı modül öznitelikleri belirtilemez

bir derlemedeki iki dosyada farklı parametre listelerine sahip [Modül](../../windows/module-cpp.md) öznitelikleri bulundu. Her derleme için yalnızca bir benzersiz `module` özniteliği belirtilebilir.

Özdeş `module` öznitelikleri, birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki `module` öznitelikleri bulunursa:

```cpp
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

Ardından,

```cpp
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

Derleyici C3171 oluşturur (farklı sürüm değerlerini göz önünde).
