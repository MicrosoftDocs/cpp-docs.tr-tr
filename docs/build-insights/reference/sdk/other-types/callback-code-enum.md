---
title: CALLBACK_CODE numaralandırması
description: C++ Derleme ÖNGÖRÜLERI SDK CALLBACK_CODE enum başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 68eaa9aa04d2f0a55ac12fb7dde14a080188a38d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332469"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE numaralandırması

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`CALLBACK_CODE` numaralandırması, bir analiz veya yeniden günlüğe kaydetme oturumunun akışını kontrol etmek için kullanılır. Sonra ne olması gerektiğini denetlemek için [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) veya [RELOG_CALLBACKS](relog-callbacks-struct.md) işlevlerdeki CALLBACK_CODE bir değer döndürün.

## <a name="members"></a>Üyeler

| Adı | Değer | Açıklama |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | Geçerli çözümlemeye devam edin veya oturumu normal olarak yeniden günlüğe yazın. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | Geçerli analizi iptal edin veya oturumu yeniden günlüğe yazın ve bir hata sinyali yapın. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | Geçerli analizi veya yeniden günlüğe kaydetme oturumunu iptal edin. |

::: moniker-end
