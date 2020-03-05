---
title: TRANSLATION_UNIT_PASS_CODE numaralandırması
description: C++ Derleme ÖNGÖRÜLERI SDK TRANSLATION_UNIT_PASS_CODE enum başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1219eed98fd01e8c91d8750977e2d8ca4498d649
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333582"
---
# <a name="translation_unit_pass_code-enum"></a>TRANSLATION_UNIT_PASS_CODE numaralandırması

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TRANSLATION_UNIT_PASS_CODE` numaralandırması.

## <a name="members"></a>Üyeler

| Adı | Değer | Açıklama |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x00000000) | Ön uç geçişi, kaynak kodu ayrıştırılmasından ve ara dile dönüştürülürken sorumludur. |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | Ara dili iyileştirmekten ve makine koduna dönüştürülürken sorumlu olan arka uç geçişi. |

## <a name="remarks"></a>Açıklamalar

C SDK işlevleri tarafından kullanılır.

::: moniker-end
