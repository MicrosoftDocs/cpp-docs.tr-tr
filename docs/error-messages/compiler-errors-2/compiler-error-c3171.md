---
title: Derleyici Hatası C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 602c9ca1051646fca2c5788c036354047fad2522
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175445"
---
# <a name="compiler-error-c3171"></a>Derleyici Hatası C3171

'module': bir projede farklı modül öznitelikleri belirtilemez

[Modül](../../windows/module-cpp.md) farklı parametre listeleri özniteliklerle iki derleme dosyalarında bulundu. Yalnızca bir benzersiz `module` derlemesi başına özniteliği belirtilebilir.

Aynı `module` öznitelikleri birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki `module` öznitelikler bulundu:

```
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

Ardından,

```
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

Derleyici C3171 üretir (farklı sürümü değerlerine dikkat edin).