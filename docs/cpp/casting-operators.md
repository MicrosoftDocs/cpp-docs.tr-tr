---
title: Atama İşleçleri
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: 606e8b159bb7bdb7527d33a5211cb33a26913754
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221828"
---
# <a name="casting-operators"></a>Atama İşleçleri

C++ diline özgü birkaç atama işleci vardır. Bu işleçler, eski stil C dili atamalarında bulunan belirsizliğin ve tehlikenin bir kısmının giderilmesini amaçlar. Bu işleçler şunlardır:

- [dynamic_cast](../cpp/dynamic-cast-operator.md) Polimorfik türlerin dönüştürülmesi için kullanılır.

- [static_cast](../cpp/static-cast-operator.md) Polimorfik olmayan türlerin dönüştürülmesi için kullanılır.

- [const_cast](../cpp/const-cast-operator.md) **`const`**, Ve özniteliklerini kaldırmak için kullanılır **`volatile`** **`__unaligned`** .

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) Bitlerin basit yeniden yorumu için kullanılır.

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) C++/CLı ' da doğrulanabilir MSIL oluşturmak için kullanılır.

**`const_cast`** **`reinterpret_cast`** Bu işleçler eski stil yayınları olarak aynı tehlikeleri sunduğundan son çare olarak ve kullanın. Bununla birlikte, eski stil atamaları tamamen değiştirmek için gereklidirler.

## <a name="see-also"></a>Ayrıca bkz.

[Atama](../cpp/casting.md)
