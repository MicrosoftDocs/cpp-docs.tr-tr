---
description: 'Daha fazla bilgi edinin: atama Işleçleri'
title: Atama İşleçleri
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: 6ab19f1b30958f4d78a97be76c15373ed9c9b620
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308555"
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
