---
title: AnalysisControl sabit listesi sınıfı
description: C++ Build Insights SDK AnalysisControl numaralandırma başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0f4887d626c5e80a0afaa393e255f8ffedbd6b1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922627"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl sabit listesi sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`AnalysisControl`Enum sınıfı, bir analiz veya yeniden günlüğe kaydetme oturumunun akışını kontrol etmek için kullanılır. `AnalysisControl`Bir sonraki ne olacağını denetlemek için bir [ıanalyzer](ianalyzer-class.md) veya [ıregünlükçü](irelogger-class.md) üye işlevinden bir kod döndürün.

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `BLOCK` | Geçerli olayın çözümleyici veya yeniden günlükçü grubunda daha fazla yayılmasını önler. |
| `CANCEL` | Geçerli analizi veya yeniden günlüğe kaydetme oturumunu iptal edin. |
| `CONTINUE` | Geçerli çözümlemeye devam edin veya oturumu normal olarak yeniden günlüğe yazın. Geçerli olayı bir sonraki çözümleyici veya yeniden günlükçü grubu üyesine yay. |
| `FAILURE` | Geçerli analizi iptal edin veya oturumu yeniden günlüğe yazın ve bir hata sinyali yapın. |

::: moniker-end
