---
title: StopTracingSessionW
description: C++ Build Insights SDK StopTracingSessionW fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6582e477ac6b13319ab5ab0f77295517548f7068
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323532"
---
# <a name="stoptracingsessionw"></a>StopTracingSessionW

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `StopTracingSessionW` devam eden bir izleme oturumunu durdurur ve ham bir izleme dosyası üretir. Ham izleme dosyaları analiz oturumu başlatmak için [Analyze,](analyze.md) [AnalzeA](analyze-a.md)ve [AnalyzeW](analyze-w.md) işlevlerine geçirilebilir. Ham izleme dosyaları da [oturumyeniden başlatmak](relog.md)için Relog , [RelogA](relog-a.md)ve [RelogW](relog-w.md) işlevleri geçirilebilir. Arayarak çağıran `StopTracingSessionW` yürütülebilirlerin yönetici ayrıcalıkları olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StopTracingSessionW(
    const wchar_t*              sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Parametreler

*Oturumadı*\
Durdurmak için izleme oturumunun adı. [StartTracingSession , StartTracingSessionA](start-tracing-session.md)veya [StartTracingSessionW'e](start-tracing-session-w.md)geçen oturum adı ile aynı oturum adını kullanın. [StartTracingSessionA](start-tracing-session-a.md)

*outputLogFile*\
Ham izlemenin kaydedilmesi gereken son çıktı günlüğü dosyasına giden yol.

*Istatistik*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) bir nesneye işaretçi. `StopTracingSessionW`dönmeden önce bu nesneye izleme toplama istatistikleri yazar.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

::: moniker-end
