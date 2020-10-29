---
title: StopTracingSession
description: C++ Build Insights SDK 'Sı StopTracingSession işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8c1455e737435aa82b32cb44a52e46e55df70d6a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922638"
---
# <a name="stoptracingsession"></a>StopTracingSession

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`StopTracingSession`İşlev devam eden bir izleme oturumunu durduruyor ve ham izleme dosyası oluşturuyor. Ham izleme dosyaları analiz oturumu başlatmak için [Çözümle](analyze.md), [AnalzeA](analyze-a.md)ve analiz [ZEW](analyze-w.md) işlevlerine geçirilebilir. Ham izleme dosyaları, yeniden günlüğe kaydetme oturumu başlatmak için [relog](relog.md), [Reloga](relog-a.md)ve [relogw](relog-w.md) işlevlerine de geçirilebilir. Çağıran yürütülebilir dosyalar `StopTracingSession` yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
inline RESULT_CODE StopTracingSession(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);

inline RESULT_CODE StopTracingSession(
    const wchar_t*              sessionName
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Parametreler

*OturumAdı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*outputLogFile*\
Ham izlemenin kaydedileceği son çıkış günlüğü dosyasının yolu.

*girecek*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopTracingSession` döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
