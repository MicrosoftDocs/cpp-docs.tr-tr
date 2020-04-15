---
title: StopAndAnalyzeTracingSession
description: C++ Build Insights SDK StopAndAnalyzeTracingSession fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c9bd4a092c22dfcdfb6d463b74207ec11ee6d64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323699"
---
# <a name="stopandanalyzetracingsession"></a>StopAndAnalyzeTracingSession

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `StopAndAnalyzeTracingSession` devam eden bir izleme oturumunu durdurur ve ortaya çıkan izlemeyi geçici bir dosyaya kaydeder. Bir analiz oturumu sonra hemen bir giriş olarak geçici dosya kullanmaya başlar. Bu işlevi çağıran yürütülebilirlerin yönetici ayrıcalıkları olmalıdır.

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

*Oturumadı*\
Durdurmak için izleme oturumunun adı. [StartTracingSession , StartTracingSessionA](start-tracing-session.md)veya [StartTracingSessionW'e](start-tracing-session-w.md)geçen oturum adı ile aynı oturum adını kullanın. [StartTracingSessionA](start-tracing-session-a.md)

*numberOfAnalysisPasses*\
İz üzerinde çalışacak analiz sayısı geçer. İz, analiz başına bir kez sağlanan analizör grubundan geçirilir.

*Istatistik*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) bir nesneye işaretçi. `StopAndAnalyzeTracingSession`dönmeden önce bu nesneye izleme toplama istatistikleri yazar.

*analyzerGroup*\
Analiz için kullanılan analizci grubu. Bir çözümleyici grubu oluşturmak için [MakeStaticAnalyzerGroup'u](make-static-analyzer-group.md) arayın. [MakeDynamicAnalyzerGroup'tan](make-dynamic-analyzer-group.md)elde edilen dinamik bir analizci grubu kullanmak isterseniz, önce adresini statik bir çözümleyici grubuna `MakeStaticAnalyzerGroup`geçirerek .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

::: moniker-end
