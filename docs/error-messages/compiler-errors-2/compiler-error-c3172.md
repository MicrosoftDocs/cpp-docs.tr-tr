---
title: Derleyici hatası C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 1da2676d660d23e3fb71b56263779b1f1edacbf9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761744"
---
# <a name="compiler-error-c3172"></a>Derleyici hatası C3172

' module_name ': bir projede farklı idl_module öznitelikleri belirtilemez

aynı ada sahip, ancak bir derlemede farklı `dllname` veya `version` parametrelere sahip [idl_module](../../windows/idl-module.md) öznitelikleri bulundu. Her derleme için yalnızca bir benzersiz `idl_module` özniteliği belirtilebilir.

Özdeş `idl_module` öznitelikleri, birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki `idl_module` öznitelikleri bulunursa:

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
