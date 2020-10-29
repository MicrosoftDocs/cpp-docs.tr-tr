---
title: CALLBACK_CODE numaralandırması
description: C++ Build Insights SDK 'Sı CALLBACK_CODE enum başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146d191d0b642ad538f5a314016b41fdbdf26113
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922600"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE numaralandırması

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`CALLBACK_CODE`Enum, bir analiz veya yeniden günlüğe kaydetme oturumunun akışını kontrol etmek için kullanılır. Sonra ne olması gerektiğini denetlemek için [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) veya [RELOG_CALLBACKS](relog-callbacks-struct.md) işlevlerdeki CALLBACK_CODE bir değer döndürün.

## <a name="members"></a>Üyeler

| Ad | Değer | Açıklama |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | Geçerli çözümlemeye devam edin veya oturumu normal olarak yeniden günlüğe yazın. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | Geçerli analizi iptal edin veya oturumu yeniden günlüğe yazın ve bir hata sinyali yapın. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | Geçerli analizi veya yeniden günlüğe kaydetme oturumunu iptal edin. |

::: moniker-end
