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
ms.openlocfilehash: a7b7fc0ce404f414b3ec07449bdc110d578fa101
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042023"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl sabit listesi sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`AnalysisControl`Enum sınıfı, bir analiz veya yeniden günlüğe kaydetme oturumunun akışını kontrol etmek için kullanılır. `AnalysisControl`Bir sonraki ne olacağını denetlemek için bir [ıanalyzer](ianalyzer-class.md) veya [ıregünlükçü](irelogger-class.md) üye işlevinden bir kod döndürün.

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `BLOCK` | Geçerli olayın çözümleyici veya yeniden günlükçü grubunda daha fazla yayılmasını önler. |
| `CANCEL` | Geçerli analizi veya yeniden günlüğe kaydetme oturumunu iptal edin. |
| `CONTINUE` | Geçerli çözümlemeye devam edin veya oturumu normal olarak yeniden günlüğe yazın. Geçerli olayı bir sonraki çözümleyici veya yeniden günlükçü grubu üyesine yay. |
| `FAILURE` | Geçerli analizi iptal edin veya oturumu yeniden günlüğe yazın ve bir hata sinyali yapın. |

::: moniker-end
