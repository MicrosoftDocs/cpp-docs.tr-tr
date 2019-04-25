---
title: Derleyici Hatası C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 5c9c1561b63c740b9f7f5d85b2bf3e04de2542c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175192"
---
# <a name="compiler-error-c3172"></a>Derleyici Hatası C3172

'module_name': bir projede farklı idl_module öznitelikleri belirtilemez

[idl_module](../../windows/idl-module.md) öznitelikleri aynı ad ancak farklı `dllname` veya `version` iki derleme dosyalarında parametreler bulundu. Yalnızca bir benzersiz `idl_module` derlemesi başına özniteliği belirtilebilir.

Aynı `idl_module` öznitelikleri birden fazla kaynak kodu dosyasında belirtilebilir.

Örneğin, aşağıdaki `idl_module` öznitelikler bulundu:

```
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

Ardından,

```
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

Derleyici C3172 üretir (farklı sürümü değerlerine dikkat edin).