---
title: StopAndAnalyzeTracingSessionA
description: C++ Build Insights SDK Stopandçözümleyiciler Etracingsessiona işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fa5adfca2c5e4d3d4bd17abae4e78c2ac6464773
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922722"
---
# <a name="stopandanalyzetracingsessiona"></a>StopAndAnalyzeTracingSessionA

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSessionA`İşlevi devam eden bir izleme oturumunu sonlandırır ve elde edilen izlemeyi geçici bir dosyaya kaydeder. Daha sonra bir analiz oturumu, giriş olarak geçici dosyayı kullanmaya hemen başlatılır. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionA(
    const char*                 sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>Parametreler

*OturumAdı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*girecek*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopAndAnalyzeTracingSessionA` döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

*analysisDescriptor*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) nesnesine yönelik işaretçi. Tarafından başlatılan analiz oturumunu yapılandırmak için bu nesneyi kullanın `StopAndAnalyzeTracingSessionA` .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
