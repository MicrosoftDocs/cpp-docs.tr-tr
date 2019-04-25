---
title: Derleyici Hatası C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: 5ef39e4580601dd90b5695d9115902bb5b834409
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174711"
---
# <a name="compiler-error-c3170"></a>Derleyici Hatası C3170

bir projede farklı modül tanımlayıcıları olamaz

[Modül](../../windows/module-cpp.md) öznitelikleri farklı adlara sahip iki derleme dosyalarında bulundu. Yalnızca bir benzersiz `module` derlemesi başına özniteliği belirtilebilir.

Aynı `module` öznitelikleri birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki modül öznitelikleri bulunamazsa:

```
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

Ardından,

```
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

Derleyici C3170 üretir (farklı adlarını not edin).