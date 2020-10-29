---
title: StopAndAnalyzeTracingSession
description: C++ Build Insights SDK Stopandçözümleyicileri Etracingsession işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81a8ce43ecedfa51874508193637969411ae52d6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922710"
---
# <a name="stopandanalyzetracingsession"></a>StopAndAnalyzeTracingSession

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSession`İşlevi devam eden bir izleme oturumunu sonlandırır ve elde edilen izlemeyi geçici bir dosyaya kaydeder. Daha sonra bir analiz oturumu, giriş olarak geçici dosyayı kullanmaya hemen başlatılır. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const char*                                   sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const wchar_t*                                sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Parametreler

*OturumAdı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*Numberofanalysispass*\
İzleme üzerinde çalıştırılacak analiz geçişi sayısı. İzleme, her analiz geçişi için belirtilen çözümleyici grubundan bir kez geçirilir.

*girecek*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopAndAnalyzeTracingSession` döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

*Analiz Zergrubu*\
Analiz için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın. [Makedynamicanalizzergroup](make-dynamic-analyzer-group.md)'tan edinilen bir dinamik çözümleyici grubunu kullanmak istiyorsanız, önce adresini adresine geçirerek bir statik çözümleyici grubu içinde kapsülleyebilirsiniz `MakeStaticAnalyzerGroup` .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
