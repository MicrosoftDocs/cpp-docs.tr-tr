---
title: TRANSLATION_UNIT_PASS_CODE numaralandırması
description: C++ Build Insights SDK 'Sı TRANSLATION_UNIT_PASS_CODE enum başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 31f3e16ce6d9aa8c3c9db6cf9c11069dc3ec22fe
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920924"
---
# <a name="translation_unit_pass_code-enum"></a>TRANSLATION_UNIT_PASS_CODE numaralandırması

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TRANSLATION_UNIT_PASS_CODE`Sabit listesi.

## <a name="members"></a>Üyeler

| Ad | Değer | Açıklama |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x00000000) | Ön uç geçişi, kaynak kodu ayrıştırılmasından ve ara dile dönüştürülürken sorumludur. |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | Ara dili iyileştirmekten ve makine koduna dönüştürülürken sorumlu olan arka uç geçişi. |

## <a name="remarks"></a>Açıklamalar

C SDK işlevleri tarafından kullanılır.

::: moniker-end
