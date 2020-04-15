---
title: Relog
description: C++ Build Insights SDK Relog işlevi başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28b290d2bf2880ce2f534fa1cd91750890e2fead
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323787"
---
# <a name="relog"></a>Relog

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev, `Relog` Windows için Olay İzleme (ETW) izleme sinden MSVC olaylarını okumak ve bunları yeni, değiştirilmiş bir ETW izlemesine yazmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const char*                                   inputLogFile,
    const char*                                   outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const wchar_t*                                inputLogFile,
    const wchar_t*                                outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>Parametreler

*TAnalyzerGroupÜyeleri*\
Bu parametre her zaman çıkarılır.

*TReloggerGroupÜyeleri*\
Bu parametre her zaman çıkarılır.

*inputLogFile*\
Olayları okumak istediğiniz giriş ETW izi.

*outputLogFile*\
Yeni olayların yazılabilmek için dosya.

*numberOfAnalysisPasses*\
Giriş izleme üzerinde çalıştırmak için çözümleme geçer sayısı. İz, analiz başına bir kez sağlanan analizör grubundan geçirilir.

*systemEventsRetentionFlags*\
Hangi sistem ETW olayları relogged izleme tutmak için belirtir bir bitmask. Daha fazla bilgi için [RELOG_RETENTION_SYSTEM_EVENT_FLAGS.](../other-types/relog-retention-system-event-flags-constants.md)

*analyzerGroup*\
Yeniden ağaçlandırma oturumunun analiz aşaması için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [MakeStaticAnalyzerGroup'u](make-static-analyzer-group.md) arayın. [MakeDynamicAnalyzerGroup'tan](make-dynamic-analyzer-group.md)elde edilen dinamik bir analizör grubunu kullanmak için, önce adresini statik `MakeStaticAnalyzerGroup`bir çözümleyici grubuna ileterek kapsülle.

*reloggerGroup*\
Olayları *outputLogFile'de*belirtilen izleme dosyasına yeniden kaydeden relogger grubu. Bir relogger grubu oluşturmak için [MakeStaticReloggerGroup'u](make-static-relogger-group.md) arayın. [MakeDynamicReloggerGroup'tan](make-dynamic-relogger-group.md)elde edilen dinamik bir relogger grubunu kullanmak için, `MakeStaticReloggerGroup`önce adresini .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

### <a name="remark"></a>Açıklama

Giriş izleme çözümleyici grup numarası *OfAnalysisPasses* kez geçirilir. Geçişleri yeniden günlüğe kaydetme seçeneği benzer bir seçenek yoktur. İz, tüm analiz geçişleri tamamlandıktan sonra relogger grubuna yalnızca bir kez geçirilir.

Bir relogger sınıfı içinden CPU örnekleri gibi sistem olaylarının yeniden günlüğe kaydedilmesi desteklenmez. Çıkış takibinde hangi sistem olaylarının kullanılacağına karar vermek için *sistemEventsRetentionFlags* parametresini kullanın.

::: moniker-end
