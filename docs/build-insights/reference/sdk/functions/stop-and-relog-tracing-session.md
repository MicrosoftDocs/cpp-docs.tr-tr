---
title: StopAndRelogTracingSession
description: C++ BUILD Insights SDK StopAndRelogTracingSession işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e99568f9b509b89ccd0f0711433dec9d96d904bc
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332595"
---
# <a name="stopandrelogtracingsession"></a>StopAndRelogTracingSession

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`StopAndRelogTracingSession` işlevi devam eden bir izleme oturumunu durduruyor ve elde edilen izlemeyi geçici bir dosyaya kaydeder. Yeniden günlüğe kaydetme oturumu daha sonra giriş olarak geçici dosyayı kullanmaya hemen başlatılır. Yeniden günlüğe kaydetme oturumu tarafından üretilen son yeniden günlüğe kaydetme izlemesi, çağıran tarafından belirtilen bir dosyaya kaydedilir. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

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

*oturumadı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*Outputlogfile*\
Yeniden günlüğe kaydetme oturumu tarafından üretilen yeniden oturum açan izlemenin yazılacağı dosya.

*istatistikler*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopAndRelogTracingSession`, döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

*Numberofanalysispass*\
İzleme üzerinde çalıştırılacak analiz geçişi sayısı. İzleme, her analiz geçişi için belirtilen çözümleyici grubundan bir kez geçirilir.

*systemEventsRetentionFlags*\
Yeniden günlüğe kaydedilen izlemede hangi sistem ETW olaylarını tutacağız belirten [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) bir bit maskesi.

*analiz Zergrubu*\
Yeniden günlüğe kaydetme oturumunun analiz aşaması için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın. [Makedynamicanalizzergroup](make-dynamic-analyzer-group.md)'tan elde edilen dinamik bir çözümleyici grubunu kullanmak istiyorsanız, önce adresini `MakeStaticAnalyzerGroup`adresine geçirerek statik bir çözümleyici grubu içinde kapsülleyebilirsiniz.

*Reloggergroup*\
Olayları *Outputlogfile*içinde belirtilen izleme dosyasına yeniden kaydeden yeniden günlükçü grubu. Bir yeniden günlükçü grubu oluşturmak için [Makestaticreloggergroup](make-static-relogger-group.md) öğesini çağırın. [Makedynamicreloggergroup](make-dynamic-relogger-group.md)öğesinden elde edilen dinamik bir yeniden günlükçü grubunu kullanmak istiyorsanız, önce adresini `MakeStaticReloggerGroup`adresine geçirerek statik bir yeniden günlükçüsü grubu içinde kapsülleyebilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

### <a name="remarks"></a>Açıklamalar

Giriş izlemesi, çözümleyici grubu *Numberofanalysispass* süreleri aracılığıyla geçirilir. Yeniden günlüğe kaydetme geçişleri için benzer bir seçenek yoktur. İzleme, tüm analiz geçişleri tamamlandıktan sonra yeniden günlükçü grubuna yalnızca bir kez Trough geçirilir.

Yeniden günlükçü sınıfı içindeki CPU örnekleri gibi sistem olaylarının yeniden günlüğe kaydedilmesi desteklenmez. Çıkış izlemesinde tutulacak sistem olaylarını belirlemek için *systemEventsRetentionFlags* parametresini kullanın.

::: moniker-end
