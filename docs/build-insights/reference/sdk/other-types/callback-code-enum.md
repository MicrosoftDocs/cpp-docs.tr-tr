---
title: CALLBACK_CODE enum
description: C++ Build Insights SDK CALLBACK_CODE enum referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d0d3dcc70040f562cd40755188e545f709a807b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329186"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE enum

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Enum `CALLBACK_CODE` bir analiz veya yeniden oturum akışını kontrol kullanılır. [ANALYSIS_CALLBACKS'daki](analysis-callbacks-struct.md) işlevlerden CALLBACK_CODE bir değer döndürün veya bundan sonra ne olacağını denetlemek [için RELOG_CALLBACKS.](relog-callbacks-struct.md)

## <a name="members"></a>Üyeler

| Adı | Değer | Açıklama |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | Geçerli çözümleme veya oturumu normal olarak yeniden kaydetmeye devam edin. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | Geçerli çözümlemesi veya oturumu yeniden günlüğe kaydetmeyi iptal edin ve bir hata sinyali verdi. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | Geçerli çözümlemesi veya oturumu yeniden günlüğe kaydetmeyi iptal edin. |

::: moniker-end
