---
title: StopAndRelogTracingSession
description: C++ derleme öngörüleri SDK StopAndRelogTracingSession işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d36dee1b16ca467d16b22587abe3ef34ee6ccb29
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919962"
---
# <a name="stopandrelogtracingsession"></a>StopAndRelogTracingSession

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSession`İşlevi devam eden bir izleme oturumunu sonlandırır ve elde edilen izlemeyi geçici bir dosyaya kaydeder. Yeniden günlüğe kaydetme oturumu daha sonra giriş olarak geçici dosyayı kullanmaya hemen başlatılır. Yeniden günlüğe kaydetme oturumu tarafından üretilen son yeniden günlüğe kaydetme izlemesi, çağıran tarafından belirtilen bir dosyaya kaydedilir. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

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

*OturumAdı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*outputLogFile*\
Yeniden günlüğe kaydetme oturumu tarafından üretilen yeniden oturum açan izlemenin yazılacağı dosya.

*girecek*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopAndRelogTracingSession` döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

*Numberofanalysispass*\
İzleme üzerinde çalıştırılacak analiz geçişi sayısı. İzleme, her analiz geçişi için belirtilen çözümleyici grubundan bir kez geçirilir.

*systemEventsRetentionFlags*\
Yeniden günlüğe kaydedilen izlemede hangi sistem ETW olaylarını tutacağız belirten [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) bir bit maskesi.

*Analiz Zergrubu*\
Yeniden günlüğe kaydetme oturumunun analiz aşaması için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın. [Makedynamicanalizzergroup](make-dynamic-analyzer-group.md)'tan edinilen bir dinamik çözümleyici grubunu kullanmak istiyorsanız, önce adresini adresine geçirerek bir statik çözümleyici grubu içinde kapsülleyebilirsiniz `MakeStaticAnalyzerGroup` .

*reloggerGroup*\
Olayları *Outputlogfile* içinde belirtilen izleme dosyasına yeniden kaydeden yeniden günlükçü grubu. Bir yeniden günlükçü grubu oluşturmak için [Makestaticreloggergroup](make-static-relogger-group.md) öğesini çağırın. [Makedynamicreloggergroup](make-dynamic-relogger-group.md)öğesinden elde edilen dinamik bir yeniden günlükçü grubunu kullanmak istiyorsanız, önce adresini adresine geçirerek statik bir yeniden günlükçüsü grubu içinde kapsülleyebilirsiniz `MakeStaticReloggerGroup` .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

### <a name="remarks"></a>Açıklamalar

Giriş izlemesi, çözümleyici grubu *Numberofanalysispass* süreleri aracılığıyla geçirilir. Yeniden günlüğe kaydetme geçişleri için benzer bir seçenek yoktur. İzleme, tüm analiz geçişleri tamamlandıktan sonra yeniden günlükçü grubuna yalnızca bir kez Trough geçirilir.

Yeniden günlükçü sınıfı içindeki CPU örnekleri gibi sistem olaylarının yeniden günlüğe kaydedilmesi desteklenmez. Çıkış izlemesinde tutulacak sistem olaylarını belirlemek için *systemEventsRetentionFlags* parametresini kullanın.

::: moniker-end
