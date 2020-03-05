---
title: Relog
description: C++ Build Insights SDK 'sı relog işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1ce09101deebd957de4b9305762dc37f38b53f4e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332693"
---
# <a name="relog"></a>Relog

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Relog` işlevi, Windows için olay Izleme (ETW) izlemesinin MSVC olaylarını okumak ve bunları yeni, değiştirilmiş bir ETW izlemeye yazmak için kullanılır.

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

*Treloggergroupmembers*\
Bu parametre her zaman çıkarılır.

*ınputlogfile*\
Olaylarını okumak istediğiniz giriş ETW izlemesi.

*Outputlogfile*\
Yeni olayların yazılacağı dosya.

*Numberofanalysispass*\
Giriş izlemede çalıştırılacak analiz geçişi sayısı. İzleme, her analiz geçişi için belirtilen çözümleyici grubundan bir kez geçirilir.

*systemEventsRetentionFlags*\
Yeniden günlüğe kaydedilen izlemede tutulacak sistem ETW olaylarını belirten bir bit maskesi. Daha fazla bilgi için bkz. [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md).

*analiz Zergrubu*\
Yeniden günlüğe kaydetme oturumunun analiz aşaması için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın. [Makedynamicanalizzergroup](make-dynamic-analyzer-group.md)'tan elde edilen dinamik bir çözümleyici grubunu kullanmak için, önce adresini `MakeStaticAnalyzerGroup`adresine geçirerek bir statik çözümleyici grubu içinde kapsülleyebilirsiniz.

*Reloggergroup*\
Olayları *Outputlogfile*içinde belirtilen izleme dosyasına yeniden kaydeden yeniden günlükçü grubu. Bir yeniden günlükçü grubu oluşturmak için [Makestaticreloggergroup](make-static-relogger-group.md) öğesini çağırın. [Makedynamicreloggergroup](make-dynamic-relogger-group.md)'dan elde edilen dinamik bir yeniden günlükçü grubunu kullanmak için, önce adresini `MakeStaticReloggerGroup`geçirerek bir statik yeniden günlükçüsü grubu içinde kapsülleyebilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

### <a name="remark"></a>Görüyorum

Giriş izlemesi, çözümleyici grubu *Numberofanalysispass* süreleri aracılığıyla geçirilir. Yeniden günlüğe kaydetme geçişleri için benzer bir seçenek yoktur. İzleme, tüm analiz geçişleri tamamlandıktan sonra yeniden günlükçü grubuna yalnızca bir kez Trough geçirilir.

Yeniden günlükçü sınıfı içindeki CPU örnekleri gibi sistem olaylarının yeniden günlüğe kaydedilmesi desteklenmez. Çıkış izlemesinde tutulacak sistem olaylarını belirlemek için *systemEventsRetentionFlags* parametresini kullanın.

::: moniker-end
