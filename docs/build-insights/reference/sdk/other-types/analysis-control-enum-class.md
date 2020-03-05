---
title: AnalysisControl sabit listesi sınıfı
description: C++ BUILD Insights SDK analysiscontrol numaralandırma başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf162c11e0a7109b8d733dab79df80782398e14d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332504"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl sabit listesi sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`AnalysisControl` enum sınıfı, bir analiz veya yeniden günlüğe kaydetme oturumunun akışını kontrol etmek için kullanılır. Bir sonraki ne olması gerektiğini denetlemek için bir [ıanalyzer](ianalyzer-class.md) veya [ıregünlükçü](irelogger-class.md) üye işlevinden bir `AnalysisControl` kodu döndürün.

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `BLOCK` | Geçerli olayın çözümleyici veya yeniden günlükçü grubunda daha fazla yayılmasını önler. |
| `CANCEL` | Geçerli analizi veya yeniden günlüğe kaydetme oturumunu iptal edin. |
| `CONTINUE` | Geçerli çözümlemeye devam edin veya oturumu normal olarak yeniden günlüğe yazın. Geçerli olayı bir sonraki çözümleyici veya yeniden günlükçü grubu üyesine yay. |
| `FAILURE` | Geçerli analizi iptal edin veya oturumu yeniden günlüğe yazın ve bir hata sinyali yapın. |

::: moniker-end
