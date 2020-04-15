---
title: AnalysisControl enum sınıfı
description: C++ Build Insights SDK AnalysisControl enum referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9431f878390127f2cefbe8f0ee42ca509e147de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323636"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl enum sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Enum `AnalysisControl` sınıfı, bir analiz in akışını veya yeniden günlüğe kaydetme oturumunu kontrol etmek için kullanılır. Bundan `AnalysisControl` sonra ne olacağını denetlemek için bir [IAnalyzer](ianalyzer-class.md) veya [IRelogger](irelogger-class.md) üye işlevinden bir kod döndürün.

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `BLOCK` | Geçerli olayın çözümleyici veya relogger grubunda daha fazla yayılmasını önler. |
| `CANCEL` | Geçerli çözümlemesi veya oturumu yeniden günlüğe kaydetmeyi iptal edin. |
| `CONTINUE` | Geçerli çözümleme veya oturumu normal olarak yeniden kaydetmeye devam edin. Geçerli olayı bir sonraki çözümleyiciye veya relogger grup üyesine yayıltın. |
| `FAILURE` | Geçerli çözümlemesi veya oturumu yeniden günlüğe kaydetmeyi iptal edin ve bir hata sinyali verdi. |

::: moniker-end
