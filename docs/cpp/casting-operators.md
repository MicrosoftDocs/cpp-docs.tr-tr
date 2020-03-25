---
title: Atama İşleçleri
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: eac274a0207be675b8d13532c3110c6e71bd55c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190111"
---
# <a name="casting-operators"></a>Atama İşleçleri

C++ diline özgü birkaç atama işleci vardır. Bu işleçler, eski stil C dili atamalarında bulunan belirsizliğin ve tehlikenin bir kısmının giderilmesini amaçlar. Bu işleçler şunlardır:

- [dynamic_cast](../cpp/dynamic-cast-operator.md) Polimorfik türlerin dönüştürülmesi için kullanılır.

- [static_cast](../cpp/static-cast-operator.md) Polimorfik olmayan türlerin dönüştürülmesi için kullanılır.

- [const_cast](../cpp/const-cast-operator.md) **Const**, **volatile**ve **__unaligned** özniteliklerini kaldırmak için kullanılır.

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) Bitlerin basit yeniden yorumu için kullanılır.

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) /CLI içinde C++doğrulanabilir MSIL oluşturmak için kullanılır.

**Const_cast** ve **reinterpret_cast** son çare olarak kullanın, çünkü bu işleçler eski stil yayınları ile aynı tehlikeleri sunar. Bununla birlikte, eski stil atamaları tamamen değiştirmek için gereklidirler.

## <a name="see-also"></a>Ayrıca bkz.

[Atama](../cpp/casting.md)
