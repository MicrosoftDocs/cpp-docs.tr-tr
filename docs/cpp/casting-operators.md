---
title: Atama İşleçleri
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: e2ac8e9079b1d30dca077363bbb6cef35960902e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768958"
---
# <a name="casting-operators"></a>Atama İşleçleri

C++ diline özgü birkaç atama işleci vardır. Bu işleçler, eski stil C dili atamalarında bulunan belirsizliğin ve tehlikenin bir kısmının giderilmesini amaçlar. Bu işleçler şunlardır:

- [dynamic_cast](../cpp/dynamic-cast-operator.md) çok biçimli türlerin dönüştürülmesi için kullanılır.

- [static_cast](../cpp/static-cast-operator.md) dönüştürme olmayan türlerin dönüştürülmesi için kullanılır.

- [const_cast](../cpp/const-cast-operator.md) kaldırmak için kullanılan **const**, **geçici**, ve **__unaligned** öznitelikleri.

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) bitlerin basit reinterpretation için kullanılır.

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) kullanılan C + +/ CLI doğrulanabilir MSIL oluşturmak için.

Kullanım **const_cast** ve **reinterpret_cast** bu işleçler eski stil atamaları olarak aynı tehlikeleri arz ettiği atamalarla son çare olarak. Bununla birlikte, eski stil atamaları tamamen değiştirmek için gereklidirler.

## <a name="see-also"></a>Ayrıca bkz.

[Atama](../cpp/casting.md)