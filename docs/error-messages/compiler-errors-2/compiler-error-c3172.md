---
title: Derleyici Hatası C3172 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25c3b1fd9132c6b170fdf74b1619a35d83959f90
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117646"
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