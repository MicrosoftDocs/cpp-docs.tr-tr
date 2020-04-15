---
title: StopAndAnalyzeTracingSessionA
description: C++ Build Insights SDK StopAndAnalyzeTracingSessionA fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 51a979b68cd87c5e7fd07b28acec80c2d7b81cf6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323728"
---
# <a name="stopandanalyzetracingsessiona"></a>StopAndAnalyzeTracingSessionA

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `StopAndAnalyzeTracingSessionA` devam eden bir izleme oturumunu durdurur ve ortaya çıkan izlemeyi geçici bir dosyaya kaydeder. Bir analiz oturumu sonra hemen bir giriş olarak geçici dosya kullanmaya başlar. Bu işlevi çağıran yürütülebilirlerin yönetici ayrıcalıkları olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionA(
    const char*                 sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>Parametreler

*Oturumadı*\
Durdurmak için izleme oturumunun adı. [StartTracingSession , StartTracingSessionA](start-tracing-session.md)veya [StartTracingSessionW'e](start-tracing-session-w.md)geçen oturum adı ile aynı oturum adını kullanın. [StartTracingSessionA](start-tracing-session-a.md)

*Istatistik*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) bir nesneye işaretçi. `StopAndAnalyzeTracingSessionA`dönmeden önce bu nesneye izleme toplama istatistikleri yazar.

*analizAçıklayıcı*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) bir nesneye işaretçi. 'tarafından başlatılan `StopAndAnalyzeTracingSessionA`çözümleme oturumunu yapılandırmak için bu nesneyi kullanın

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

::: moniker-end
