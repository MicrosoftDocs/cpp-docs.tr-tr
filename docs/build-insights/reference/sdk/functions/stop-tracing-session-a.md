---
title: StopTracingSessionA
description: C++ Build Insights SDK 'Sı StopTracingSessionA işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 12f0c7a9665c47f36fb5e88d799673918017bb98
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332588"
---
# <a name="stoptracingsessiona"></a>StopTracingSessionA

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`StopTracingSessionA` işlevi devam eden bir izleme oturumunu durduruyor ve ham izleme dosyası oluşturuyor. Ham izleme dosyaları analiz oturumu başlatmak için [Çözümle](analyze.md), [AnalzeA](analyze-a.md)ve analiz [ZEW](analyze-w.md) işlevlerine geçirilebilir. Ham izleme dosyaları, yeniden günlüğe kaydetme oturumunu başlatmak için [relog](relog.md), [Reloga](relog-a.md)ve [relogw](relog-w.md) işlevlerine de geçirilebilir. `StopTracingSessionA` çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Parametreler

*oturumadı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*Outputlogfile*\
Ham izlemenin kaydedileceği son çıkış günlüğü dosyasının yolu.

*istatistikler*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopTracingSessionA`, döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
