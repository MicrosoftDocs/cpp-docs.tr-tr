---
title: Relog
description: C++ derleme öngörüleri SDK 'Sı relog işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 628f60042a10cf80c0b077d28387ed75466e925b
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922757"
---
# <a name="relog"></a>Relog

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Relog`İşlevi, Windows Için olay izleme (ETW) IZLEMESININ MSVC olaylarını okumak ve bunları yeni, değiştirilmiş BIR ETW izlemeye yazmak için kullanılır.

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

*TAnalyzerGroupMembers*\
Bu parametre her zaman çıkarılır.

*TReloggerGroupMembers*\
Bu parametre her zaman çıkarılır.

*ınputlogfile*\
Olaylarını okumak istediğiniz giriş ETW izlemesi.

*outputLogFile*\
Yeni olayların yazılacağı dosya.

*Numberofanalysispass*\
Giriş izlemede çalıştırılacak analiz geçişi sayısı. İzleme, her analiz geçişi için belirtilen çözümleyici grubundan bir kez geçirilir.

*systemEventsRetentionFlags*\
Yeniden günlüğe kaydedilen izlemede tutulacak sistem ETW olaylarını belirten bir bit maskesi. Daha fazla bilgi için bkz. [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md).

*Analiz Zergrubu*\
Yeniden günlüğe kaydetme oturumunun analiz aşaması için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın. [Makedynamicanalizzergroup](make-dynamic-analyzer-group.md)'tan edinilen dinamik bir çözümleyici grubunu kullanmak için, önce adresini adresine geçirerek bir statik çözümleyici grubu içinde kapsülleyebilirsiniz `MakeStaticAnalyzerGroup` .

*reloggerGroup*\
Olayları *Outputlogfile* içinde belirtilen izleme dosyasına yeniden kaydeden yeniden günlükçü grubu. Bir yeniden günlükçü grubu oluşturmak için [Makestaticreloggergroup](make-static-relogger-group.md) öğesini çağırın. [Makedynamicreloggergroup](make-dynamic-relogger-group.md)öğesinden elde edilen dinamik bir yeniden günlükçü grubunu kullanmak için, önce adresini adresine geçirerek bir statik yeniden günlükçüsü grubu içinde kapsülleyebilirsiniz `MakeStaticReloggerGroup` .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

### <a name="remark"></a>Görüyorum

Giriş izlemesi, çözümleyici grubu *Numberofanalysispass* süreleri aracılığıyla geçirilir. Yeniden günlüğe kaydetme geçişleri için benzer bir seçenek yoktur. İzleme, tüm analiz geçişleri tamamlandıktan sonra yeniden günlükçü grubuna yalnızca bir kez Trough geçirilir.

Yeniden günlükçü sınıfı içindeki CPU örnekleri gibi sistem olaylarının yeniden günlüğe kaydedilmesi desteklenmez. Çıkış izlemesinde tutulacak sistem olaylarını belirlemek için *systemEventsRetentionFlags* parametresini kullanın.

::: moniker-end
