---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3171'
title: Derleyici hatası C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 65e7e1db9a864b894a0bce825df09a372489a79d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242203"
---
# <a name="compiler-error-c3171"></a>Derleyici hatası C3171

' Module ': bir projede farklı modül öznitelikleri belirtilemez

bir derlemedeki iki dosyada farklı parametre listelerine sahip [Modül](../../windows/attributes/module-cpp.md) öznitelikleri bulundu. `module`Her derleme için yalnızca bir benzersiz öznitelik belirtilebilir.

Aynı `module` öznitelikler birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki `module` öznitelikler bulunursa:

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
