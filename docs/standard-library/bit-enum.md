---
title: endian numaralandırması
description: skaler türlerin bitiliğini belirtmek için kullanılan Enum
ms.date: 08/27/2020
f1_keywords:
- bit/std::endian
helpviewer_keywords:
- std::endian
ms.openlocfilehash: 78df181e20d0e5d72508bd0fc86118528a312d6b
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194561"
---
# <a name="endian-enum"></a>endian numaralandırması

Tüm skaler türlerin bitiliğini gösterir.

## <a name="syntax"></a>Syntax

```cpp
enum class endian {
    little = 0,
    big = 1,
    native = little
 };
```

### <a name="members"></a>Üyeler

|Öğe|Açıklama|
|-|-|
| `little` | Skaler türlerin az endian olduğunu gösterir. Diğer bir deyişle, en az önemli bayt en küçük adreste saklanır. Örneğin, `0x1234` depolanır `0x34` `0x12` .  |
| `big` | Skaler türlerin büyük endian olduğunu, yani en önemli baytın en küçük adreste depolandığını belirtir. Örneğin, `0x1234` depolanır `0x12` `0x34` .  |

## <a name="remarks"></a>Açıklamalar

Tüm yerel skaler türler, Microsoft Visual C++ hedefler (x86, x64, ARM, ARM64) için az endian 'dir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<bit>

**Ad alanı:** std

`/std:c++latest` gereklidir

## <a name="see-also"></a>Ayrıca bkz.

[\<bit>](../standard-library/bit.md)  
