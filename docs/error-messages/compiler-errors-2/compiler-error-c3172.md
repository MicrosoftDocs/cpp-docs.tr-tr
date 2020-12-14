---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3172'
title: Derleyici hatası C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: d8ce88960e725266723c3c37cd9bfbbbd342027b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242177"
---
# <a name="compiler-error-c3172"></a>Derleyici hatası C3172

' module_name ': bir projede farklı idl_module öznitelikleri belirtilemez

[](../../windows/attributes/idl-module.md) `dllname` derleme içindeki dosyaların ikisi de aynı ada sahip ancak farklı veya parametrelere sahip idl_module öznitelikleri `version` bulundu. `idl_module`Her derleme için yalnızca bir benzersiz öznitelik belirtilebilir.

Aynı `idl_module` öznitelikler birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki `idl_module` öznitelikler bulunursa:

```cpp
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

Ardından,

```cpp
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

Derleyici C3172 oluşturur (farklı sürüm değerlerini göz önünde).
