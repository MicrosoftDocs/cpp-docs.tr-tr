---
title: Derleyici Hatası C3170 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7a193abcd59c3e9454eec1108f1e3bbb66efcc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070372"
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