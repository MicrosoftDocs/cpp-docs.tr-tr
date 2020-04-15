---
title: StopAndRelogTracingOturum
description: C++ Build Insights SDK StopAndRelogTracingSession fonksiyonu referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1f6f5af63d25504226707d977791430463374328
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323662"
---
# <a name="stopandrelogtracingsession"></a>StopAndRelogTracingOturum

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `StopAndRelogTracingSession` devam eden bir izleme oturumunu durdurur ve ortaya çıkan izlemeyi geçici bir dosyaya kaydeder. Yeniden günlüğe kaydetme oturumu daha sonra geçici dosyayı giriş olarak kullanmaya başlar. Yeniden günlüğe kaydetme oturumu tarafından üretilen son yeniden kaydedilmiş izleme, arayan tarafından belirtilen bir dosyaya kaydedilir. Bu işlevi çağıran yürütülebilirlerin yönetici ayrıcalıkları olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const char*                                   sessionName,
    const char*                                   outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const wchar_t*                                sessionName,
    const wchar_t*                                outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>Parametreler

*Oturumadı*\
Durdurmak için izleme oturumunun adı. [StartTracingSession , StartTracingSessionA](start-tracing-session.md)veya [StartTracingSessionW'e](start-tracing-session-w.md)geçen oturum adı ile aynı oturum adını kullanın. [StartTracingSessionA](start-tracing-session-a.md)

*outputLogFile*\
Yeniden ağaçlandırılmak üzere üretilen relogged izin yazılabilmek için dosya.

*Istatistik*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) bir nesneye işaretçi. `StopAndRelogTracingSession`dönmeden önce bu nesneye izleme toplama istatistikleri yazar.

*numberOfAnalysisPasses*\
İz üzerinde çalışacak analiz sayısı geçer. İz, analiz başına bir kez sağlanan analizör grubundan geçirilir.

*systemEventsRetentionFlags*\
Hangi sistem ETW olayları relogged izleme tutmak için belirtir [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) bir bitmask.

*analyzerGroup*\
Yeniden ağaçlandırma oturumunun analiz aşaması için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [MakeStaticAnalyzerGroup'u](make-static-analyzer-group.md) arayın. [MakeDynamicAnalyzerGroup'tan](make-dynamic-analyzer-group.md)elde edilen dinamik bir analizci grubu kullanmak isterseniz, önce adresini statik bir çözümleyici grubuna `MakeStaticAnalyzerGroup`geçirerek .

*reloggerGroup*\
Olayları *outputLogFile'de*belirtilen izleme dosyasına yeniden kaydeden relogger grubu. Bir relogger grubu oluşturmak için [MakeStaticReloggerGroup'u](make-static-relogger-group.md) arayın. [MakeDynamicReloggerGroup'tan](make-dynamic-relogger-group.md)elde edilen dinamik bir relogger grubu kullanmak isterseniz, önce adresini ' e geçirerek `MakeStaticReloggerGroup`statik bir relogger grubu içinde kapsüllersiniz.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

### <a name="remarks"></a>Açıklamalar

Giriş izleme çözümleyici grup numarası *OfAnalysisPasses* kez geçirilir. Geçişleri yeniden günlüğe kaydetme seçeneği benzer bir seçenek yoktur. İz, tüm analiz geçişleri tamamlandıktan sonra relogger grubuna yalnızca bir kez geçirilir.

Bir relogger sınıfı içinden CPU örnekleri gibi sistem olaylarının yeniden günlüğe kaydedilmesi desteklenmez. Çıkış takibinde hangi sistem olaylarının kullanılacağına karar vermek için *sistemEventsRetentionFlags* parametresini kullanın.

::: moniker-end
